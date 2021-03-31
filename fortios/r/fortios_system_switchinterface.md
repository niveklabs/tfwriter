# fortios_system_switchinterface

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
module "fortios_system_switchinterface" {
  source = "./modules/fortios/r/fortios_system_switchinterface"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # intra_switch_policy - (optional) is a type of string
  intra_switch_policy = null
  # mac_ttl - (optional) is a type of number
  mac_ttl = null
  # name - (required) is a type of string
  name = null
  # span - (optional) is a type of string
  span = null
  # span_dest_port - (optional) is a type of string
  span_dest_port = null
  # span_direction - (optional) is a type of string
  span_direction = null
  # type - (optional) is a type of string
  type = null
  # vdom - (optional) is a type of string
  vdom = null

  member = [{
    interface_name = null
  }]

  span_source_port = [{
    interface_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intra_switch_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "span" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "span_dest_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "span_direction" {
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

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}

variable "span_source_port" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_switchinterface" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  intra_switch_policy   = var.intra_switch_policy
  mac_ttl               = var.mac_ttl
  name                  = var.name
  span                  = var.span
  span_dest_port        = var.span_dest_port
  span_direction        = var.span_direction
  type                  = var.type
  vdom                  = var.vdom

  dynamic "member" {
    for_each = var.member
    content {
      interface_name = member.value["interface_name"]
    }
  }

  dynamic "span_source_port" {
    for_each = var.span_source_port
    content {
      interface_name = span_source_port.value["interface_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.id
}

output "intra_switch_policy" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.intra_switch_policy
}

output "mac_ttl" {
  description = "returns a number"
  value       = fortios_system_switchinterface.this.mac_ttl
}

output "span" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.span
}

output "span_dest_port" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.span_dest_port
}

output "span_direction" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.span_direction
}

output "type" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.type
}

output "vdom" {
  description = "returns a string"
  value       = fortios_system_switchinterface.this.vdom
}

output "this" {
  value = fortios_system_switchinterface.this
}
```

[top](#index)