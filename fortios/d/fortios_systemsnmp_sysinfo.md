# fortios_systemsnmp_sysinfo

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
module "fortios_systemsnmp_sysinfo" {
  source = "./modules/fortios/d/fortios_systemsnmp_sysinfo"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_systemsnmp_sysinfo" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "contact_info" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_sysinfo.this.contact_info
}

output "description" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_sysinfo.this.description
}

output "engine_id" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_sysinfo.this.engine_id
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_sysinfo.this.id
}

output "location" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_sysinfo.this.location
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_sysinfo.this.status
}

output "trap_high_cpu_threshold" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_sysinfo.this.trap_high_cpu_threshold
}

output "trap_log_full_threshold" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_sysinfo.this.trap_log_full_threshold
}

output "trap_low_memory_threshold" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_sysinfo.this.trap_low_memory_threshold
}

output "this" {
  value = fortios_systemsnmp_sysinfo.this
}
```

[top](#index)