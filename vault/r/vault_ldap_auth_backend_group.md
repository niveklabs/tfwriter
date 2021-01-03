# vault_ldap_auth_backend_group

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
module "vault_ldap_auth_backend_group" {
  source = "./modules/vault/r/vault_ldap_auth_backend_group"

  # backend - (optional) is a type of string
  backend = null
  # groupname - (required) is a type of string
  groupname = null
  # policies - (optional) is a type of set of string
  policies = []
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

variable "groupname" {
  description = "(required)"
  type        = string
}

variable "policies" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_ldap_auth_backend_group" "this" {
  backend   = var.backend
  groupname = var.groupname
  policies  = var.policies
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_ldap_auth_backend_group.this.id
}

output "policies" {
  description = "returns a set of string"
  value       = vault_ldap_auth_backend_group.this.policies
}

output "this" {
  value = vault_ldap_auth_backend_group.this
}
```

[top](#index)