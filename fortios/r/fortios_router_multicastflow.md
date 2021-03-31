# fortios_router_multicastflow

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
module "fortios_router_multicastflow" {
  source = "./modules/fortios/r/fortios_router_multicastflow"

  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  flows = [{
    group_addr  = null
    id          = null
    source_addr = null
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

variable "flows" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      group_addr  = string
      id          = number
      source_addr = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_multicastflow" "this" {
  comments              = var.comments
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "flows" {
    for_each = var.flows
    content {
      group_addr  = flows.value["group_addr"]
      id          = flows.value["id"]
      source_addr = flows.value["source_addr"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = fortios_router_multicastflow.this.comments
}

output "id" {
  description = "returns a string"
  value       = fortios_router_multicastflow.this.id
}

output "this" {
  value = fortios_router_multicastflow.this
}
```

[top](#index)