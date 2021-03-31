# fortios_wirelesscontrollerhotspot20_anqpipaddresstype

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
module "fortios_wirelesscontrollerhotspot20_anqpipaddresstype" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqpipaddresstype"

  # ipv4_address_type - (optional) is a type of string
  ipv4_address_type = null
  # ipv6_address_type - (optional) is a type of string
  ipv6_address_type = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "ipv4_address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_address_type" {
  description = "(optional)"
  type        = string
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
resource "fortios_wirelesscontrollerhotspot20_anqpipaddresstype" "this" {
  ipv4_address_type = var.ipv4_address_type
  ipv6_address_type = var.ipv6_address_type
  name              = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpipaddresstype.this.id
}

output "ipv4_address_type" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpipaddresstype.this.ipv4_address_type
}

output "ipv6_address_type" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpipaddresstype.this.ipv6_address_type
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpipaddresstype.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_anqpipaddresstype.this
}
```

[top](#index)