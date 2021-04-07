# fortios_router_bfd

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
module "fortios_router_bfd" {
  source = "./modules/fortios/r/fortios_router_bfd"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null

  neighbor = [{
    interface = null
    ip        = null
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

variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface = string
      ip        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_bfd" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      # interface - (optional) is a type of string
      interface = neighbor.value["interface"]
      # ip - (optional) is a type of string
      ip = neighbor.value["ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_bfd.this.id
}

output "this" {
  value = fortios_router_bfd.this
}
```

[top](#index)