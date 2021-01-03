# vault_ldap_auth_backend_user

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
module "vault_ldap_auth_backend_user" {
  source = "./modules/vault/r/vault_ldap_auth_backend_user"

  # backend - (optional) is a type of string
  backend = null
  # groups - (optional) is a type of set of string
  groups = []
  # policies - (optional) is a type of set of string
  policies = []
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "policies" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_ldap_auth_backend_user" "this" {
  backend  = var.backend
  groups   = var.groups
  policies = var.policies
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a set of string"
  value       = vault_ldap_auth_backend_user.this.groups
}

output "id" {
  description = "returns a string"
  value       = vault_ldap_auth_backend_user.this.id
}

output "policies" {
  description = "returns a set of string"
  value       = vault_ldap_auth_backend_user.this.policies
}

output "this" {
  value = vault_ldap_auth_backend_user.this
}
```

[top](#index)