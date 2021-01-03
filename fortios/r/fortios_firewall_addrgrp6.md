# fortios_firewall_addrgrp6

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
module "fortios_firewall_addrgrp6" {
  source = "./modules/fortios/r/fortios_firewall_addrgrp6"

  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # name - (optional) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null
  # visibility - (optional) is a type of string
  visibility = null

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

variable "visibility" {
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
resource "fortios_firewall_addrgrp6" "this" {
  color      = var.color
  comment    = var.comment
  name       = var.name
  uuid       = var.uuid
  visibility = var.visibility

  dynamic "member" {
    for_each = var.member
    content {
      name = member.value["name"]
    }
  }

  dynamic "tagging" {
    for_each = var.tagging
    content {
      category = tagging.value["category"]
      name     = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
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
output "color" {
  description = "returns a number"
  value       = fortios_firewall_addrgrp6.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp6.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp6.this.name
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp6.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewall_addrgrp6.this.visibility
}

output "this" {
  value = fortios_firewall_addrgrp6.this
}
```

[top](#index)