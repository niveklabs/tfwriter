# vault_gcp_secret_roleset

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
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_gcp_secret_roleset" {
  source = "./modules/vault/r/vault_gcp_secret_roleset"

  # backend - (required) is a type of string
  backend = null
  # project - (required) is a type of string
  project = null
  # roleset - (required) is a type of string
  roleset = null
  # secret_type - (optional) is a type of string
  secret_type = null
  # token_scopes - (optional) is a type of set of string
  token_scopes = []

  binding = [{
    resource = null
    roles    = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - Path where the GCP secrets engine is mounted."
  type        = string
}

variable "project" {
  description = "(required) - Name of the GCP project that this roleset's service account will belong to."
  type        = string
}

variable "roleset" {
  description = "(required) - Name of the RoleSet to create"
  type        = string
}

variable "secret_type" {
  description = "(optional) - Type of secret generated for this role set. Defaults to `access_token`. Accepted values: `access_token`, `service_account_key`"
  type        = string
  default     = null
}

variable "token_scopes" {
  description = "(optional) - List of OAuth scopes to assign to `access_token` secrets generated under this role set (`access_token` role sets only) "
  type        = set(string)
  default     = null
}

variable "binding" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      resource = string
      roles    = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vault_gcp_secret_roleset" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # project - (required) is a type of string
  project = var.project
  # roleset - (required) is a type of string
  roleset = var.roleset
  # secret_type - (optional) is a type of string
  secret_type = var.secret_type
  # token_scopes - (optional) is a type of set of string
  token_scopes = var.token_scopes

  dynamic "binding" {
    for_each = var.binding
    content {
      # resource - (required) is a type of string
      resource = binding.value["resource"]
      # roles - (required) is a type of set of string
      roles = binding.value["roles"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_gcp_secret_roleset.this.id
}

output "secret_type" {
  description = "returns a string"
  value       = vault_gcp_secret_roleset.this.secret_type
}

output "service_account_email" {
  description = "returns a string"
  value       = vault_gcp_secret_roleset.this.service_account_email
}

output "this" {
  value = vault_gcp_secret_roleset.this
}
```

[top](#index)