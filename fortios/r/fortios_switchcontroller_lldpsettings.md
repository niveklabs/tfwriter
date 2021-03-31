# fortios_switchcontroller_lldpsettings

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
module "fortios_switchcontroller_lldpsettings" {
  source = "./modules/fortios/r/fortios_switchcontroller_lldpsettings"

  # device_detection - (optional) is a type of string
  device_detection = null
  # fast_start_interval - (optional) is a type of number
  fast_start_interval = null
  # management_interface - (optional) is a type of string
  management_interface = null
  # status - (optional) is a type of string
  status = null
  # tx_hold - (optional) is a type of number
  tx_hold = null
  # tx_interval - (optional) is a type of number
  tx_interval = null
}
```

[top](#index)

### Variables

```terraform
variable "device_detection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fast_start_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "management_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tx_hold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tx_interval" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_lldpsettings" "this" {
  device_detection     = var.device_detection
  fast_start_interval  = var.fast_start_interval
  management_interface = var.management_interface
  status               = var.status
  tx_hold              = var.tx_hold
  tx_interval          = var.tx_interval
}
```

[top](#index)

### Outputs

```terraform
output "device_detection" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpsettings.this.device_detection
}

output "fast_start_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_lldpsettings.this.fast_start_interval
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpsettings.this.id
}

output "management_interface" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpsettings.this.management_interface
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpsettings.this.status
}

output "tx_hold" {
  description = "returns a number"
  value       = fortios_switchcontroller_lldpsettings.this.tx_hold
}

output "tx_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_lldpsettings.this.tx_interval
}

output "this" {
  value = fortios_switchcontroller_lldpsettings.this
}
```

[top](#index)