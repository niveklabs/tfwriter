# fortios_firewallwildcardfqdn_custom

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
module "fortios_firewallwildcardfqdn_custom" {
  source = "./modules/fortios/r/fortios_firewallwildcardfqdn_custom"

  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # name - (optional) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null
  # visibility - (optional) is a type of string
  visibility = null
  # wildcard_fqdn - (optional) is a type of string
  wildcard_fqdn = null
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wildcard_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallwildcardfqdn_custom" "this" {
  color         = var.color
  comment       = var.comment
  name          = var.name
  uuid          = var.uuid
  visibility    = var.visibility
  wildcard_fqdn = var.wildcard_fqdn
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = fortios_firewallwildcardfqdn_custom.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallwildcardfqdn_custom.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallwildcardfqdn_custom.this.name
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewallwildcardfqdn_custom.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewallwildcardfqdn_custom.this.visibility
}

output "wildcard_fqdn" {
  description = "returns a string"
  value       = fortios_firewallwildcardfqdn_custom.this.wildcard_fqdn
}

output "this" {
  value = fortios_firewallwildcardfqdn_custom.this
}
```

[top](#index)