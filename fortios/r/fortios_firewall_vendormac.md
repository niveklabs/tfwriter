# fortios_firewall_vendormac

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
module "fortios_firewall_vendormac" {
  source = "./modules/fortios/r/fortios_firewall_vendormac"

  # fosid - (optional) is a type of number
  fosid = null
  # mac_number - (optional) is a type of number
  mac_number = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_vendormac" "this" {
  fosid      = var.fosid
  mac_number = var.mac_number
  name       = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_vendormac.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_vendormac.this.id
}

output "mac_number" {
  description = "returns a number"
  value       = fortios_firewall_vendormac.this.mac_number
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_vendormac.this.name
}

output "this" {
  value = fortios_firewall_vendormac.this
}
```

[top](#index)