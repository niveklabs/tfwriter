# fortios_system_fm

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
module "fortios_system_fm" {
  source = "./modules/fortios/d/fortios_system_fm"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_fm" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "auto_backup" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.auto_backup
}

output "fosid" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.fosid
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.ip
}

output "ipsec" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.ipsec
}

output "scheduled_config_restore" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.scheduled_config_restore
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.status
}

output "vdom" {
  description = "returns a string"
  value       = data.fortios_system_fm.this.vdom
}

output "this" {
  value = fortios_system_fm.this
}
```

[top](#index)