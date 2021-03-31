# fortios_system_fortimanager

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
module "fortios_system_fortimanager" {
  source = "./modules/fortios/d/fortios_system_fortimanager"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_fortimanager" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "central_management" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.central_management
}

output "central_mgmt_auto_backup" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.central_mgmt_auto_backup
}

output "central_mgmt_schedule_config_restore" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.central_mgmt_schedule_config_restore
}

output "central_mgmt_schedule_script_restore" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.central_mgmt_schedule_script_restore
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.ip
}

output "ipsec" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.ipsec
}

output "vdom" {
  description = "returns a string"
  value       = data.fortios_system_fortimanager.this.vdom
}

output "this" {
  value = fortios_system_fortimanager.this
}
```

[top](#index)