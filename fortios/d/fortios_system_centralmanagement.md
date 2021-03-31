# fortios_system_centralmanagement

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_system_centralmanagement"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_centralmanagement" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "allow_monitor" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.allow_monitor
}

output "allow_push_configuration" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.allow_push_configuration
}

output "allow_push_firmware" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.allow_push_firmware
}

output "allow_remote_firmware_upgrade" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.allow_remote_firmware_upgrade
}

output "ca_cert" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.ca_cert
}

output "enc_algorithm" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.enc_algorithm
}

output "fmg" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.fmg
}

output "fmg_source_ip" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.fmg_source_ip
}

output "fmg_source_ip6" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.fmg_source_ip6
}

output "fmg_update_port" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.fmg_update_port
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.id
}

output "include_default_servers" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.include_default_servers
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.interface_select_method
}

output "local_cert" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.local_cert
}

output "mode" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.mode
}

output "schedule_config_restore" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.schedule_config_restore
}

output "schedule_script_restore" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.schedule_script_restore
}

output "serial_number" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.serial_number
}

output "server_list" {
  description = "returns a list of object"
  value       = data.fortios_system_centralmanagement.this.server_list
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.type
}

output "vdom" {
  description = "returns a string"
  value       = data.fortios_system_centralmanagement.this.vdom
}

output "this" {
  value = fortios_system_centralmanagement.this
}
```

[top](#index)