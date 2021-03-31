# vault_okta_auth_backend_user

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
module "vault_okta_auth_backend_user" {
  source = "./modules/vault/r/vault_okta_auth_backend_user"

  # groups - (optional) is a type of set of string
  groups = []
  # path - (required) is a type of string
  path = null
  # policies - (optional) is a type of set of string
  policies = []
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "groups" {
  description = "(optional) - Groups within the Okta auth backend to associate with this user"
  type        = set(string)
  default     = null
}

variable "path" {
  description = "(required) - Path to the Okta auth backend"
  type        = string
}

variable "policies" {
  description = "(optional) - Policies to associate with this user"
  type        = set(string)
  default     = null
}

variable "username" {
  description = "(required) - Name of the user within Okta"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_okta_auth_backend_user" "this" {
  groups   = var.groups
  path     = var.path
  policies = var.policies
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_okta_auth_backend_user.this.id
}

output "this" {
  value = vault_okta_auth_backend_user.this
}
```

[top](#index)