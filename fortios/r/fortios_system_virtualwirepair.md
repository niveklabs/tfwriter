# fortios_system_virtualwirepair

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
module "fortios_system_virtualwirepair" {
  source = "./modules/fortios/r/fortios_system_virtualwirepair"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # vlan_filter - (optional) is a type of string
  vlan_filter = null
  # wildcard_vlan - (optional) is a type of string
  wildcard_vlan = null

  member = [{
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wildcard_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_virtualwirepair" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # vlan_filter - (optional) is a type of string
  vlan_filter = var.vlan_filter
  # wildcard_vlan - (optional) is a type of string
  wildcard_vlan = var.wildcard_vlan

  dynamic "member" {
    for_each = var.member
    content {
      # interface_name - (optional) is a type of string
      interface_name = member.value["interface_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_virtualwirepair.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_virtualwirepair.this.name
}

output "vlan_filter" {
  description = "returns a string"
  value       = fortios_system_virtualwirepair.this.vlan_filter
}

output "wildcard_vlan" {
  description = "returns a string"
  value       = fortios_system_virtualwirepair.this.wildcard_vlan
}

output "this" {
  value = fortios_system_virtualwirepair.this
}
```

[top](#index)