# fortios_router_prefixlist

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
module "fortios_router_prefixlist" {
  source = "./modules/fortios/r/fortios_router_prefixlist"

  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  rule = [{
    action = null
    flags  = null
    ge     = null
    id     = null
    le     = null
    prefix = null
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
      action = string
      flags  = number
      ge     = number
      id     = number
      le     = number
      prefix = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_prefixlist" "this" {
  comments              = var.comments
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      action = rule.value["action"]
      flags  = rule.value["flags"]
      ge     = rule.value["ge"]
      id     = rule.value["id"]
      le     = rule.value["le"]
      prefix = rule.value["prefix"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = fortios_router_prefixlist.this.comments
}

output "id" {
  description = "returns a string"
  value       = fortios_router_prefixlist.this.id
}

output "this" {
  value = fortios_router_prefixlist.this
}
```

[top](#index)