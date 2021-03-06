# fortios_system_centralmanagement

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
module "fortios_system_centralmanagement" {
  source = "./modules/fortios/r/fortios_system_centralmanagement"

  # allow_monitor - (optional) is a type of string
  allow_monitor = null
  # allow_push_configuration - (optional) is a type of string
  allow_push_configuration = null
  # allow_push_firmware - (optional) is a type of string
  allow_push_firmware = null
  # allow_remote_firmware_upgrade - (optional) is a type of string
  allow_remote_firmware_upgrade = null
  # ca_cert - (optional) is a type of string
  ca_cert = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = null
  # fmg - (optional) is a type of string
  fmg = null
  # fmg_source_ip - (optional) is a type of string
  fmg_source_ip = null
  # fmg_source_ip6 - (optional) is a type of string
  fmg_source_ip6 = null
  # fmg_update_port - (optional) is a type of string
  fmg_update_port = null
  # include_default_servers - (optional) is a type of string
  include_default_servers = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # local_cert - (optional) is a type of string
  local_cert = null
  # mode - (optional) is a type of string
  mode = null
  # schedule_config_restore - (optional) is a type of string
  schedule_config_restore = null
  # schedule_script_restore - (optional) is a type of string
  schedule_script_restore = null
  # serial_number - (optional) is a type of string
  serial_number = null
  # type - (optional) is a type of string
  type = null
  # vdom - (optional) is a type of string
  vdom = null

  server_list = [{
    addr_type       = null
    fqdn            = null
    id              = null
    server_address  = null
    server_address6 = null
    server_type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_monitor" {
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

variable "allow_remote_firmware_upgrade" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enc_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fmg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fmg_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fmg_source_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fmg_update_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_default_servers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_config_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_script_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr_type       = string
      fqdn            = string
      id              = number
      server_address  = string
      server_address6 = string
      server_type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_centralmanagement" "this" {
  # allow_monitor - (optional) is a type of string
  allow_monitor = var.allow_monitor
  # allow_push_configuration - (optional) is a type of string
  allow_push_configuration = var.allow_push_configuration
  # allow_push_firmware - (optional) is a type of string
  allow_push_firmware = var.allow_push_firmware
  # allow_remote_firmware_upgrade - (optional) is a type of string
  allow_remote_firmware_upgrade = var.allow_remote_firmware_upgrade
  # ca_cert - (optional) is a type of string
  ca_cert = var.ca_cert
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # enc_algorithm - (optional) is a type of string
  enc_algorithm = var.enc_algorithm
  # fmg - (optional) is a type of string
  fmg = var.fmg
  # fmg_source_ip - (optional) is a type of string
  fmg_source_ip = var.fmg_source_ip
  # fmg_source_ip6 - (optional) is a type of string
  fmg_source_ip6 = var.fmg_source_ip6
  # fmg_update_port - (optional) is a type of string
  fmg_update_port = var.fmg_update_port
  # include_default_servers - (optional) is a type of string
  include_default_servers = var.include_default_servers
  # interface - (optional) is a type of string
  interface = var.interface
  # interface_select_method - (optional) is a type of string
  interface_select_method = var.interface_select_method
  # local_cert - (optional) is a type of string
  local_cert = var.local_cert
  # mode - (optional) is a type of string
  mode = var.mode
  # schedule_config_restore - (optional) is a type of string
  schedule_config_restore = var.schedule_config_restore
  # schedule_script_restore - (optional) is a type of string
  schedule_script_restore = var.schedule_script_restore
  # serial_number - (optional) is a type of string
  serial_number = var.serial_number
  # type - (optional) is a type of string
  type = var.type
  # vdom - (optional) is a type of string
  vdom = var.vdom

  dynamic "server_list" {
    for_each = var.server_list
    content {
      # addr_type - (optional) is a type of string
      addr_type = server_list.value["addr_type"]
      # fqdn - (optional) is a type of string
      fqdn = server_list.value["fqdn"]
      # id - (optional) is a type of number
      id = server_list.value["id"]
      # server_address - (optional) is a type of string
      server_address = server_list.value["server_address"]
      # server_address6 - (optional) is a type of string
      server_address6 = server_list.value["server_address6"]
      # server_type - (optional) is a type of string
      server_type = server_list.value["server_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_monitor" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.allow_monitor
}

output "allow_push_configuration" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.allow_push_configuration
}

output "allow_push_firmware" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.allow_push_firmware
}

output "allow_remote_firmware_upgrade" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.allow_remote_firmware_upgrade
}

output "ca_cert" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.ca_cert
}

output "enc_algorithm" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.enc_algorithm
}

output "fmg" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.fmg
}

output "fmg_source_ip" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.fmg_source_ip
}

output "fmg_source_ip6" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.fmg_source_ip6
}

output "fmg_update_port" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.fmg_update_port
}

output "id" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.id
}

output "include_default_servers" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.include_default_servers
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.interface_select_method
}

output "local_cert" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.local_cert
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.mode
}

output "schedule_config_restore" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.schedule_config_restore
}

output "schedule_script_restore" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.schedule_script_restore
}

output "serial_number" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.serial_number
}

output "type" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.type
}

output "vdom" {
  description = "returns a string"
  value       = fortios_system_centralmanagement.this.vdom
}

output "this" {
  value = fortios_system_centralmanagement.this
}
```

[top](#index)