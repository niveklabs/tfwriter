# fortios_firewall_multicastaddress6

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
module "fortios_firewall_multicastaddress6" {
  source = "./modules/fortios/r/fortios_firewall_multicastaddress6"

  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ip6 - (required) is a type of string
  ip6 = null
  # name - (optional) is a type of string
  name = null
  # visibility - (optional) is a type of string
  visibility = null

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

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "fortios_firewall_multicastaddress6" "this" {
  color                 = var.color
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  ip6                   = var.ip6
  name                  = var.name
  visibility            = var.visibility

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
  value       = fortios_firewall_multicastaddress6.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress6.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress6.this.name
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress6.this.visibility
}

output "this" {
  value = fortios_firewall_multicastaddress6.this
}
```

[top](#index)