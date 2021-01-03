# fortios_endpointcontrol_settings

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
module "fortios_endpointcontrol_settings" {
  source = "./modules/fortios/r/fortios_endpointcontrol_settings"

  # download_custom_link - (optional) is a type of string
  download_custom_link = null
  # download_location - (optional) is a type of string
  download_location = null
  # forticlient_avdb_update_interval - (optional) is a type of number
  forticlient_avdb_update_interval = null
  # forticlient_dereg_unsupported_client - (optional) is a type of string
  forticlient_dereg_unsupported_client = null
  # forticlient_ems_rest_api_call_timeout - (optional) is a type of number
  forticlient_ems_rest_api_call_timeout = null
  # forticlient_keepalive_interval - (optional) is a type of number
  forticlient_keepalive_interval = null
  # forticlient_offline_grace - (optional) is a type of string
  forticlient_offline_grace = null
  # forticlient_offline_grace_interval - (optional) is a type of number
  forticlient_offline_grace_interval = null
  # forticlient_reg_key - (optional) is a type of string
  forticlient_reg_key = null
  # forticlient_reg_key_enforce - (optional) is a type of string
  forticlient_reg_key_enforce = null
  # forticlient_reg_timeout - (optional) is a type of number
  forticlient_reg_timeout = null
  # forticlient_sys_update_interval - (optional) is a type of number
  forticlient_sys_update_interval = null
  # forticlient_user_avatar - (optional) is a type of string
  forticlient_user_avatar = null
  # forticlient_warning_interval - (optional) is a type of number
  forticlient_warning_interval = null
}
```

[top](#index)

### Variables

```terraform
variable "download_custom_link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "download_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_avdb_update_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forticlient_dereg_unsupported_client" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_ems_rest_api_call_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forticlient_keepalive_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forticlient_offline_grace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_offline_grace_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forticlient_reg_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_reg_key_enforce" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_reg_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forticlient_sys_update_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forticlient_user_avatar" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_warning_interval" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_settings" "this" {
  download_custom_link                  = var.download_custom_link
  download_location                     = var.download_location
  forticlient_avdb_update_interval      = var.forticlient_avdb_update_interval
  forticlient_dereg_unsupported_client  = var.forticlient_dereg_unsupported_client
  forticlient_ems_rest_api_call_timeout = var.forticlient_ems_rest_api_call_timeout
  forticlient_keepalive_interval        = var.forticlient_keepalive_interval
  forticlient_offline_grace             = var.forticlient_offline_grace
  forticlient_offline_grace_interval    = var.forticlient_offline_grace_interval
  forticlient_reg_key                   = var.forticlient_reg_key
  forticlient_reg_key_enforce           = var.forticlient_reg_key_enforce
  forticlient_reg_timeout               = var.forticlient_reg_timeout
  forticlient_sys_update_interval       = var.forticlient_sys_update_interval
  forticlient_user_avatar               = var.forticlient_user_avatar
  forticlient_warning_interval          = var.forticlient_warning_interval
}
```

[top](#index)

### Outputs

```terraform
output "download_custom_link" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.download_custom_link
}

output "download_location" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.download_location
}

output "forticlient_avdb_update_interval" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_avdb_update_interval
}

output "forticlient_dereg_unsupported_client" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.forticlient_dereg_unsupported_client
}

output "forticlient_ems_rest_api_call_timeout" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_ems_rest_api_call_timeout
}

output "forticlient_keepalive_interval" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_keepalive_interval
}

output "forticlient_offline_grace" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.forticlient_offline_grace
}

output "forticlient_offline_grace_interval" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_offline_grace_interval
}

output "forticlient_reg_key_enforce" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.forticlient_reg_key_enforce
}

output "forticlient_reg_timeout" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_reg_timeout
}

output "forticlient_sys_update_interval" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_sys_update_interval
}

output "forticlient_user_avatar" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.forticlient_user_avatar
}

output "forticlient_warning_interval" {
  description = "returns a number"
  value       = fortios_endpointcontrol_settings.this.forticlient_warning_interval
}

output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_settings.this.id
}

output "this" {
  value = fortios_endpointcontrol_settings.this
}
```

[top](#index)