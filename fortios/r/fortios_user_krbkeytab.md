# fortios_user_krbkeytab

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_krbkeytab" {
  source = "./modules/fortios/r/fortios_user_krbkeytab"

  # keytab - (required) is a type of string
  keytab = null
  # ldap_server - (required) is a type of string
  ldap_server = null
  # name - (optional) is a type of string
  name = null
  # principal - (required) is a type of string
  principal = null
}
```

[top](#index)

### Variables

```terraform
variable "keytab" {
  description = "(required)"
  type        = string
}

variable "ldap_server" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_krbkeytab" "this" {
  keytab      = var.keytab
  ldap_server = var.ldap_server
  name        = var.name
  principal   = var.principal
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_user_krbkeytab.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_user_krbkeytab.this.name
}

output "this" {
  value = fortios_user_krbkeytab.this
}
```

[top](#index)