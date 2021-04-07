# fortios_system_fortimanager

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
module "fortios_system_fortimanager" {
  source = "./modules/fortios/r/fortios_system_fortimanager"

  # central_management - (optional) is a type of string
  central_management = null
  # central_mgmt_auto_backup - (optional) is a type of string
  central_mgmt_auto_backup = null
  # central_mgmt_schedule_config_restore - (optional) is a type of string
  central_mgmt_schedule_config_restore = null
  # central_mgmt_schedule_script_restore - (optional) is a type of string
  central_mgmt_schedule_script_restore = null
  # ip - (optional) is a type of string
  ip = null
  # ipsec - (optional) is a type of string
  ipsec = null
  # vdom - (optional) is a type of string
  vdom = null
}
```

[top](#index)

### Variables

```terraform
variable "central_management" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "central_mgmt_auto_backup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "central_mgmt_schedule_config_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "central_mgmt_schedule_script_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_fortimanager" "this" {
  # central_management - (optional) is a type of string
  central_management = var.central_management
  # central_mgmt_auto_backup - (optional) is a type of string
  central_mgmt_auto_backup = var.central_mgmt_auto_backup
  # central_mgmt_schedule_config_restore - (optional) is a type of string
  central_mgmt_schedule_config_restore = var.central_mgmt_schedule_config_restore
  # central_mgmt_schedule_script_restore - (optional) is a type of string
  central_mgmt_schedule_script_restore = var.central_mgmt_schedule_script_restore
  # ip - (optional) is a type of string
  ip = var.ip
  # ipsec - (optional) is a type of string
  ipsec = var.ipsec
  # vdom - (optional) is a type of string
  vdom = var.vdom
}
```

[top](#index)

### Outputs

```terraform
output "central_management" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.central_management
}

output "central_mgmt_auto_backup" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.central_mgmt_auto_backup
}

output "central_mgmt_schedule_config_restore" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.central_mgmt_schedule_config_restore
}

output "central_mgmt_schedule_script_restore" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.central_mgmt_schedule_script_restore
}

output "id" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.ip
}

output "ipsec" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.ipsec
}

output "vdom" {
  description = "returns a string"
  value       = fortios_system_fortimanager.this.vdom
}

output "this" {
  value = fortios_system_fortimanager.this
}
```

[top](#index)