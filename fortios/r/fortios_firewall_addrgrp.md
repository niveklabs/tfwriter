# fortios_firewall_addrgrp

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
module "fortios_firewall_addrgrp" {
  source = "./modules/fortios/r/fortios_firewall_addrgrp"

  # allow_routing - (optional) is a type of string
  allow_routing = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # exclude - (optional) is a type of string
  exclude = null
  # name - (required) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null
  # visibility - (optional) is a type of string
  visibility = null

  exclude_member = [{
    name = null
  }]

  member = [{
    name = null
  }]

  tagging = [{
    category = null
    name     = null
    tags = [{
      name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exclude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exclude_member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "member" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "tagging" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      name     = string
      tags = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_addrgrp" "this" {
  # allow_routing - (optional) is a type of string
  allow_routing = var.allow_routing
  # color - (optional) is a type of number
  color = var.color
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # exclude - (optional) is a type of string
  exclude = var.exclude
  # name - (required) is a type of string
  name = var.name
  # type - (optional) is a type of string
  type = var.type
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # visibility - (optional) is a type of string
  visibility = var.visibility

  dynamic "exclude_member" {
    for_each = var.exclude_member
    content {
      # name - (optional) is a type of string
      name = exclude_member.value["name"]
    }
  }

  dynamic "member" {
    for_each = var.member
    content {
      # name - (optional) is a type of string
      name = member.value["name"]
    }
  }

  dynamic "tagging" {
    for_each = var.tagging
    content {
      # category - (optional) is a type of string
      category = tagging.value["category"]
      # name - (optional) is a type of string
      name = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
          # name - (optional) is a type of string
          name = tags.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_routing" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp.this.allow_routing
}

output "color" {
  description = "returns a number"
  value       = fortios_firewall_addrgrp.this.color
}

output "exclude" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp.this.exclude
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp.this.id
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp.this.type
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp.this.visibility
}

output "this" {
  value = fortios_firewall_addrgrp.this
}
```

[top](#index)