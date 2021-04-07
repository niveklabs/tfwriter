# fortios_switchcontrollerqos_ipdscpmap

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
module "fortios_switchcontrollerqos_ipdscpmap" {
  source = "./modules/fortios/r/fortios_switchcontrollerqos_ipdscpmap"

  # description - (optional) is a type of string
  description = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  map = [{
    cos_queue     = null
    diffserv      = null
    ip_precedence = null
    name          = null
    value         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
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

variable "map" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cos_queue     = number
      diffserv      = string
      ip_precedence = string
      name          = string
      value         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerqos_ipdscpmap" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (required) is a type of string
  name = var.name

  dynamic "map" {
    for_each = var.map
    content {
      # cos_queue - (optional) is a type of number
      cos_queue = map.value["cos_queue"]
      # diffserv - (optional) is a type of string
      diffserv = map.value["diffserv"]
      # ip_precedence - (optional) is a type of string
      ip_precedence = map.value["ip_precedence"]
      # name - (optional) is a type of string
      name = map.value["name"]
      # value - (optional) is a type of string
      value = map.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_ipdscpmap.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_ipdscpmap.this.id
}

output "this" {
  value = fortios_switchcontrollerqos_ipdscpmap.this
}
```

[top](#index)