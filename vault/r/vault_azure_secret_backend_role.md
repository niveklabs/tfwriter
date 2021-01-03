# vault_azure_secret_backend_role

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_azure_secret_backend_role" {
  source = "./modules/vault/r/vault_azure_secret_backend_role"

  # application_object_id - (optional) is a type of string
  application_object_id = null
  # backend - (optional) is a type of string
  backend = null
  # description - (optional) is a type of string
  description = null
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # role - (required) is a type of string
  role = null
  # ttl - (optional) is a type of string
  ttl = null

  azure_groups = [{
    group_name = null
    object_id  = null
  }]

  azure_roles = [{
    role_id   = null
    role_name = null
    scope     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_object_id" {
  description = "(optional) - Application Object ID for an existing service principal that will be used instead of creating dynamic service principals."
  type        = string
  default     = null
}

variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "role" {
  description = "(required) - Name of the role to create"
  type        = string
}

variable "ttl" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "azure_groups" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      group_name = string
      object_id  = string
    }
  ))
  default = []
}

variable "azure_roles" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      role_id   = string
      role_name = string
      scope     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vault_azure_secret_backend_role" "this" {
  application_object_id = var.application_object_id
  backend               = var.backend
  description           = var.description
  max_ttl               = var.max_ttl
  role                  = var.role
  ttl                   = var.ttl

  dynamic "azure_groups" {
    for_each = var.azure_groups
    content {
      group_name = azure_groups.value["group_name"]
    }
  }

  dynamic "azure_roles" {
    for_each = var.azure_roles
    content {
      role_name = azure_roles.value["role_name"]
      scope     = azure_roles.value["scope"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_azure_secret_backend_role.this.id
}

output "this" {
  value = vault_azure_secret_backend_role.this
}
```

[top](#index)