# fortios_system_hamonitor

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
module "fortios_system_hamonitor" {
  source = "./modules/fortios/r/fortios_system_hamonitor"

  # monitor_vlan - (optional) is a type of string
  monitor_vlan = null
  # vlan_hb_interval - (optional) is a type of number
  vlan_hb_interval = null
  # vlan_hb_lost_threshold - (optional) is a type of number
  vlan_hb_lost_threshold = null
}
```

[top](#index)

### Variables

```terraform
variable "monitor_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_hb_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vlan_hb_lost_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_hamonitor" "this" {
  monitor_vlan           = var.monitor_vlan
  vlan_hb_interval       = var.vlan_hb_interval
  vlan_hb_lost_threshold = var.vlan_hb_lost_threshold
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_hamonitor.this.id
}

output "monitor_vlan" {
  description = "returns a string"
  value       = fortios_system_hamonitor.this.monitor_vlan
}

output "vlan_hb_interval" {
  description = "returns a number"
  value       = fortios_system_hamonitor.this.vlan_hb_interval
}

output "vlan_hb_lost_threshold" {
  description = "returns a number"
  value       = fortios_system_hamonitor.this.vlan_hb_lost_threshold
}

output "this" {
  value = fortios_system_hamonitor.this
}
```

[top](#index)