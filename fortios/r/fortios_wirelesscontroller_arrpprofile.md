# fortios_wirelesscontroller_arrpprofile

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
module "fortios_wirelesscontroller_arrpprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_arrpprofile"

  # comment - (optional) is a type of string
  comment = null
  # include_dfs_channel - (optional) is a type of string
  include_dfs_channel = null
  # include_weather_channel - (optional) is a type of string
  include_weather_channel = null
  # monitor_period - (optional) is a type of number
  monitor_period = null
  # name - (optional) is a type of string
  name = null
  # selection_period - (optional) is a type of number
  selection_period = null
  # threshold_ap - (optional) is a type of number
  threshold_ap = null
  # threshold_channel_load - (optional) is a type of number
  threshold_channel_load = null
  # threshold_noise_floor - (optional) is a type of string
  threshold_noise_floor = null
  # threshold_rx_errors - (optional) is a type of number
  threshold_rx_errors = null
  # threshold_spectral_rssi - (optional) is a type of string
  threshold_spectral_rssi = null
  # threshold_tx_retries - (optional) is a type of number
  threshold_tx_retries = null
  # weight_channel_load - (optional) is a type of number
  weight_channel_load = null
  # weight_dfs_channel - (optional) is a type of number
  weight_dfs_channel = null
  # weight_managed_ap - (optional) is a type of number
  weight_managed_ap = null
  # weight_noise_floor - (optional) is a type of number
  weight_noise_floor = null
  # weight_rogue_ap - (optional) is a type of number
  weight_rogue_ap = null
  # weight_spectral_rssi - (optional) is a type of number
  weight_spectral_rssi = null
  # weight_weather_channel - (optional) is a type of number
  weight_weather_channel = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_dfs_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_weather_channel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selection_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "threshold_ap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "threshold_channel_load" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "threshold_noise_floor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold_rx_errors" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "threshold_spectral_rssi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold_tx_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_channel_load" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_dfs_channel" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_managed_ap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_noise_floor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_rogue_ap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_spectral_rssi" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight_weather_channel" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_arrpprofile" "this" {
  comment                 = var.comment
  include_dfs_channel     = var.include_dfs_channel
  include_weather_channel = var.include_weather_channel
  monitor_period          = var.monitor_period
  name                    = var.name
  selection_period        = var.selection_period
  threshold_ap            = var.threshold_ap
  threshold_channel_load  = var.threshold_channel_load
  threshold_noise_floor   = var.threshold_noise_floor
  threshold_rx_errors     = var.threshold_rx_errors
  threshold_spectral_rssi = var.threshold_spectral_rssi
  threshold_tx_retries    = var.threshold_tx_retries
  weight_channel_load     = var.weight_channel_load
  weight_dfs_channel      = var.weight_dfs_channel
  weight_managed_ap       = var.weight_managed_ap
  weight_noise_floor      = var.weight_noise_floor
  weight_rogue_ap         = var.weight_rogue_ap
  weight_spectral_rssi    = var.weight_spectral_rssi
  weight_weather_channel  = var.weight_weather_channel
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_arrpprofile.this.id
}

output "include_dfs_channel" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_arrpprofile.this.include_dfs_channel
}

output "include_weather_channel" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_arrpprofile.this.include_weather_channel
}

output "monitor_period" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.monitor_period
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_arrpprofile.this.name
}

output "selection_period" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.selection_period
}

output "threshold_ap" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.threshold_ap
}

output "threshold_channel_load" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.threshold_channel_load
}

output "threshold_noise_floor" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_arrpprofile.this.threshold_noise_floor
}

output "threshold_rx_errors" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.threshold_rx_errors
}

output "threshold_spectral_rssi" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_arrpprofile.this.threshold_spectral_rssi
}

output "threshold_tx_retries" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.threshold_tx_retries
}

output "weight_channel_load" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_channel_load
}

output "weight_dfs_channel" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_dfs_channel
}

output "weight_managed_ap" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_managed_ap
}

output "weight_noise_floor" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_noise_floor
}

output "weight_rogue_ap" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_rogue_ap
}

output "weight_spectral_rssi" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_spectral_rssi
}

output "weight_weather_channel" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_arrpprofile.this.weight_weather_channel
}

output "this" {
  value = fortios_wirelesscontroller_arrpprofile.this
}
```

[top](#index)