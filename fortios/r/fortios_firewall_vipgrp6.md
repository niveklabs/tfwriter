# fortios_firewall_vipgrp6

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
module "fortios_firewall_vipgrp6" {
  source = "./modules/fortios/r/fortios_firewall_vipgrp6"

  # color - (optional) is a type of number
  color = null
  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null

  member = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_vipgrp6" "this" {
  # color - (optional) is a type of number
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "member" {
    for_each = var.member
    content {
      # name - (optional) is a type of string
      name = member.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = fortios_firewall_vipgrp6.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_vipgrp6.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_vipgrp6.this.name
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_vipgrp6.this.uuid
}

output "this" {
  value = fortios_firewall_vipgrp6.this
}
```

[top](#index)