# fortios_nsxt_servicechain

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
module "fortios_nsxt_servicechain" {
  source = "./modules/fortios/r/fortios_nsxt_servicechain"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null

  service_index = [{
    id            = null
    name          = null
    reverse_index = null
    vd            = null
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

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_index" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id            = number
      name          = string
      reverse_index = number
      vd            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_nsxt_servicechain" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid
  name                  = var.name

  dynamic "service_index" {
    for_each = var.service_index
    content {
      id            = service_index.value["id"]
      name          = service_index.value["name"]
      reverse_index = service_index.value["reverse_index"]
      vd            = service_index.value["vd"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_nsxt_servicechain.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_nsxt_servicechain.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_nsxt_servicechain.this.name
}

output "this" {
  value = fortios_nsxt_servicechain.this
}
```

[top](#index)