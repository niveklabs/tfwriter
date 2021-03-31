# fortios_router_aspathlist

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
module "fortios_router_aspathlist" {
  source = "./modules/fortios/r/fortios_router_aspathlist"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  rule = [{
    action = null
    id     = null
    regexp = null
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
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      id     = number
      regexp = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_aspathlist" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      action = rule.value["action"]
      id     = rule.value["id"]
      regexp = rule.value["regexp"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_aspathlist.this.id
}

output "this" {
  value = fortios_router_aspathlist.this
}
```

[top](#index)