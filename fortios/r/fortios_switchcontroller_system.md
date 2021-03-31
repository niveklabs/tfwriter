# fortios_switchcontroller_system

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
module "fortios_switchcontroller_system" {
  source = "./modules/fortios/r/fortios_switchcontroller_system"

  # data_sync_interval - (optional) is a type of number
  data_sync_interval = null
  # iot_holdoff - (optional) is a type of number
  iot_holdoff = null
  # iot_mac_idle - (optional) is a type of number
  iot_mac_idle = null
  # iot_scan_interval - (optional) is a type of number
  iot_scan_interval = null
  # iot_weight_threshold - (optional) is a type of number
  iot_weight_threshold = null
  # nac_periodic_interval - (optional) is a type of number
  nac_periodic_interval = null
  # parallel_process - (optional) is a type of number
  parallel_process = null
  # parallel_process_override - (optional) is a type of string
  parallel_process_override = null
}
```

[top](#index)

### Variables

```terraform
variable "data_sync_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iot_holdoff" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iot_mac_idle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iot_scan_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "iot_weight_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nac_periodic_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "parallel_process" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "parallel_process_override" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_system" "this" {
  data_sync_interval        = var.data_sync_interval
  iot_holdoff               = var.iot_holdoff
  iot_mac_idle              = var.iot_mac_idle
  iot_scan_interval         = var.iot_scan_interval
  iot_weight_threshold      = var.iot_weight_threshold
  nac_periodic_interval     = var.nac_periodic_interval
  parallel_process          = var.parallel_process
  parallel_process_override = var.parallel_process_override
}
```

[top](#index)

### Outputs

```terraform
output "data_sync_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.data_sync_interval
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_system.this.id
}

output "iot_holdoff" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.iot_holdoff
}

output "iot_mac_idle" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.iot_mac_idle
}

output "iot_scan_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.iot_scan_interval
}

output "iot_weight_threshold" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.iot_weight_threshold
}

output "nac_periodic_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.nac_periodic_interval
}

output "parallel_process" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.parallel_process
}

output "parallel_process_override" {
  description = "returns a string"
  value       = fortios_switchcontroller_system.this.parallel_process_override
}

output "this" {
  value = fortios_switchcontroller_system.this
}
```

[top](#index)