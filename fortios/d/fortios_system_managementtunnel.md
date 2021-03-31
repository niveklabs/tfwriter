# fortios_system_managementtunnel

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
module "fortios_system_managementtunnel" {
  source = "./modules/fortios/d/fortios_system_managementtunnel"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_managementtunnel" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "allow_collect_statistics" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.allow_collect_statistics
}

output "allow_config_restore" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.allow_config_restore
}

output "allow_push_configuration" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.allow_push_configuration
}

output "allow_push_firmware" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.allow_push_firmware
}

output "authorized_manager_only" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.authorized_manager_only
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.id
}

output "serial_number" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.serial_number
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_managementtunnel.this.status
}

output "this" {
  value = fortios_system_managementtunnel.this
}
```

[top](#index)