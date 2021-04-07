# fortios_system_managementtunnel

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
module "fortios_system_managementtunnel" {
  source = "./modules/fortios/r/fortios_system_managementtunnel"

  # allow_collect_statistics - (optional) is a type of string
  allow_collect_statistics = null
  # allow_config_restore - (optional) is a type of string
  allow_config_restore = null
  # allow_push_configuration - (optional) is a type of string
  allow_push_configuration = null
  # allow_push_firmware - (optional) is a type of string
  allow_push_firmware = null
  # authorized_manager_only - (optional) is a type of string
  authorized_manager_only = null
  # serial_number - (optional) is a type of string
  serial_number = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_collect_statistics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_config_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_push_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_push_firmware" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorized_manager_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_managementtunnel" "this" {
  # allow_collect_statistics - (optional) is a type of string
  allow_collect_statistics = var.allow_collect_statistics
  # allow_config_restore - (optional) is a type of string
  allow_config_restore = var.allow_config_restore
  # allow_push_configuration - (optional) is a type of string
  allow_push_configuration = var.allow_push_configuration
  # allow_push_firmware - (optional) is a type of string
  allow_push_firmware = var.allow_push_firmware
  # authorized_manager_only - (optional) is a type of string
  authorized_manager_only = var.authorized_manager_only
  # serial_number - (optional) is a type of string
  serial_number = var.serial_number
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "allow_collect_statistics" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.allow_collect_statistics
}

output "allow_config_restore" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.allow_config_restore
}

output "allow_push_configuration" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.allow_push_configuration
}

output "allow_push_firmware" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.allow_push_firmware
}

output "authorized_manager_only" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.authorized_manager_only
}

output "id" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.id
}

output "serial_number" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.serial_number
}

output "status" {
  description = "returns a string"
  value       = fortios_system_managementtunnel.this.status
}

output "this" {
  value = fortios_system_managementtunnel.this
}
```

[top](#index)