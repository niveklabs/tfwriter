# vault_okta_auth_backend_group

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
module "vault_okta_auth_backend_group" {
  source = "./modules/vault/r/vault_okta_auth_backend_group"

  # group_name - (required) is a type of string
  group_name = null
  # path - (required) is a type of string
  path = null
  # policies - (optional) is a type of set of string
  policies = []
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required) - Name of the Okta group"
  type        = string
}

variable "path" {
  description = "(required) - Path to the Okta auth backend"
  type        = string
}

variable "policies" {
  description = "(optional) - Policies to associate with this group"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_okta_auth_backend_group" "this" {
  # group_name - (required) is a type of string
  group_name = var.group_name
  # path - (required) is a type of string
  path = var.path
  # policies - (optional) is a type of set of string
  policies = var.policies
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_okta_auth_backend_group.this.id
}

output "this" {
  value = vault_okta_auth_backend_group.this
}
```

[top](#index)