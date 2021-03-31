# fortios_system_automationdestination

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
module "fortios_system_automationdestination" {
  source = "./modules/fortios/r/fortios_system_automationdestination"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ha_group_id - (optional) is a type of number
  ha_group_id = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null

  destination = [{
    name = null
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

variable "ha_group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination" {
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
resource "fortios_system_automationdestination" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  ha_group_id           = var.ha_group_id
  name                  = var.name
  type                  = var.type

  dynamic "destination" {
    for_each = var.destination
    content {
      name = destination.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ha_group_id" {
  description = "returns a number"
  value       = fortios_system_automationdestination.this.ha_group_id
}

output "id" {
  description = "returns a string"
  value       = fortios_system_automationdestination.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_automationdestination.this.name
}

output "type" {
  description = "returns a string"
  value       = fortios_system_automationdestination.this.type
}

output "this" {
  value = fortios_system_automationdestination.this
}
```

[top](#index)