# fortios_router_accesslist

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
module "fortios_router_accesslist" {
  source = "./modules/fortios/r/fortios_router_accesslist"

  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  rule = [{
    action      = null
    exact_match = null
    flags       = null
    id          = null
    prefix      = null
    wildcard    = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      exact_match = string
      flags       = number
      id          = number
      prefix      = string
      wildcard    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_accesslist" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (required) is a type of string
  name = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      # action - (optional) is a type of string
      action = rule.value["action"]
      # exact_match - (optional) is a type of string
      exact_match = rule.value["exact_match"]
      # flags - (optional) is a type of number
      flags = rule.value["flags"]
      # id - (optional) is a type of number
      id = rule.value["id"]
      # prefix - (optional) is a type of string
      prefix = rule.value["prefix"]
      # wildcard - (optional) is a type of string
      wildcard = rule.value["wildcard"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = fortios_router_accesslist.this.comments
}

output "id" {
  description = "returns a string"
  value       = fortios_router_accesslist.this.id
}

output "this" {
  value = fortios_router_accesslist.this
}
```

[top](#index)