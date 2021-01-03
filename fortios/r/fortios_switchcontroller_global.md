# fortios_switchcontroller_global

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_global" {
  source = "./modules/fortios/r/fortios_switchcontroller_global"

  # allow_multiple_interfaces - (optional) is a type of string
  allow_multiple_interfaces = null
  # default_virtual_switch_vlan - (optional) is a type of string
  default_virtual_switch_vlan = null
  # https_image_push - (optional) is a type of string
  https_image_push = null
  # log_mac_limit_violations - (optional) is a type of string
  log_mac_limit_violations = null
  # mac_aging_interval - (optional) is a type of number
  mac_aging_interval = null
  # mac_retention_period - (optional) is a type of number
  mac_retention_period = null
  # mac_violation_timer - (optional) is a type of number
  mac_violation_timer = null

  custom_command = [{
    command_entry = null
    command_name  = null
  }]

  disable_discovery = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_multiple_interfaces" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_virtual_switch_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_image_push" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_mac_limit_violations" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_aging_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac_violation_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "custom_command" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      command_entry = string
      command_name  = string
    }
  ))
  default = []
}

variable "disable_discovery" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_global" "this" {
  allow_multiple_interfaces   = var.allow_multiple_interfaces
  default_virtual_switch_vlan = var.default_virtual_switch_vlan
  https_image_push            = var.https_image_push
  log_mac_limit_violations    = var.log_mac_limit_violations
  mac_aging_interval          = var.mac_aging_interval
  mac_retention_period        = var.mac_retention_period
  mac_violation_timer         = var.mac_violation_timer

  dynamic "custom_command" {
    for_each = var.custom_command
    content {
      command_entry = custom_command.value["command_entry"]
      command_name  = custom_command.value["command_name"]
    }
  }

  dynamic "disable_discovery" {
    for_each = var.disable_discovery
    content {
      name = disable_discovery.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_multiple_interfaces" {
  description = "returns a string"
  value       = fortios_switchcontroller_global.this.allow_multiple_interfaces
}

output "default_virtual_switch_vlan" {
  description = "returns a string"
  value       = fortios_switchcontroller_global.this.default_virtual_switch_vlan
}

output "https_image_push" {
  description = "returns a string"
  value       = fortios_switchcontroller_global.this.https_image_push
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_global.this.id
}

output "log_mac_limit_violations" {
  description = "returns a string"
  value       = fortios_switchcontroller_global.this.log_mac_limit_violations
}

output "mac_aging_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_global.this.mac_aging_interval
}

output "mac_retention_period" {
  description = "returns a number"
  value       = fortios_switchcontroller_global.this.mac_retention_period
}

output "mac_violation_timer" {
  description = "returns a number"
  value       = fortios_switchcontroller_global.this.mac_violation_timer
}

output "this" {
  value = fortios_switchcontroller_global.this
}
```

[top](#index)