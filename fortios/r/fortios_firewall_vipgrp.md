# fortios_firewall_vipgrp

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
module "fortios_firewall_vipgrp" {
  source = "./modules/fortios/r/fortios_firewall_vipgrp"

  # color - (optional) is a type of number
  color = null
  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # interface - (required) is a type of string
  interface = null
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

variable "interface" {
  description = "(required)"
  type        = string
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
resource "fortios_firewall_vipgrp" "this" {
  color                 = var.color
  comments              = var.comments
  dynamic_sort_subtable = var.dynamic_sort_subtable
  interface             = var.interface
  name                  = var.name
  uuid                  = var.uuid

  dynamic "member" {
    for_each = var.member
    content {
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
  value       = fortios_firewall_vipgrp.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_vipgrp.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_vipgrp.this.name
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_vipgrp.this.uuid
}

output "this" {
  value = fortios_firewall_vipgrp.this
}
```

[top](#index)