# fortios_system_hamonitor

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
module "fortios_system_hamonitor" {
  source = "./modules/fortios/d/fortios_system_hamonitor"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_hamonitor" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_hamonitor.this.id
}

output "monitor_vlan" {
  description = "returns a string"
  value       = data.fortios_system_hamonitor.this.monitor_vlan
}

output "vlan_hb_interval" {
  description = "returns a number"
  value       = data.fortios_system_hamonitor.this.vlan_hb_interval
}

output "vlan_hb_lost_threshold" {
  description = "returns a number"
  value       = data.fortios_system_hamonitor.this.vlan_hb_lost_threshold
}

output "this" {
  value = fortios_system_hamonitor.this
}
```

[top](#index)