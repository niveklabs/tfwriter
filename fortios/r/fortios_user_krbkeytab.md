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
    fortios = ">= 1.11.0"
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
  # pac_data - (optional) is a type of string
  pac_data = null
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

variable "pac_data" {
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
  pac_data    = var.pac_data
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

output "pac_data" {
  description = "returns a string"
  value       = fortios_user_krbkeytab.this.pac_data
}

output "this" {
  value = fortios_user_krbkeytab.this
}
```

[top](#index)