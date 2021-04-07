# fortios_wirelesscontrollerhotspot20_h2qpwanmetric

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
module "fortios_wirelesscontrollerhotspot20_h2qpwanmetric" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_h2qpwanmetric"

  # downlink_load - (optional) is a type of number
  downlink_load = null
  # downlink_speed - (optional) is a type of number
  downlink_speed = null
  # link_at_capacity - (optional) is a type of string
  link_at_capacity = null
  # link_status - (optional) is a type of string
  link_status = null
  # load_measurement_duration - (optional) is a type of number
  load_measurement_duration = null
  # name - (optional) is a type of string
  name = null
  # symmetric_wan_link - (optional) is a type of string
  symmetric_wan_link = null
  # uplink_load - (optional) is a type of number
  uplink_load = null
  # uplink_speed - (optional) is a type of number
  uplink_speed = null
}
```

[top](#index)

### Variables

```terraform
variable "downlink_load" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "downlink_speed" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "link_at_capacity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_measurement_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "symmetric_wan_link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uplink_load" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uplink_speed" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_h2qpwanmetric" "this" {
  # downlink_load - (optional) is a type of number
  downlink_load = var.downlink_load
  # downlink_speed - (optional) is a type of number
  downlink_speed = var.downlink_speed
  # link_at_capacity - (optional) is a type of string
  link_at_capacity = var.link_at_capacity
  # link_status - (optional) is a type of string
  link_status = var.link_status
  # load_measurement_duration - (optional) is a type of number
  load_measurement_duration = var.load_measurement_duration
  # name - (optional) is a type of string
  name = var.name
  # symmetric_wan_link - (optional) is a type of string
  symmetric_wan_link = var.symmetric_wan_link
  # uplink_load - (optional) is a type of number
  uplink_load = var.uplink_load
  # uplink_speed - (optional) is a type of number
  uplink_speed = var.uplink_speed
}
```

[top](#index)

### Outputs

```terraform
output "downlink_load" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.downlink_load
}

output "downlink_speed" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.downlink_speed
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.id
}

output "link_at_capacity" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.link_at_capacity
}

output "link_status" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.link_status
}

output "load_measurement_duration" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.load_measurement_duration
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.name
}

output "symmetric_wan_link" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.symmetric_wan_link
}

output "uplink_load" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.uplink_load
}

output "uplink_speed" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this.uplink_speed
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_h2qpwanmetric.this
}
```

[top](#index)