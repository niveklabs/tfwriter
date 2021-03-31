# fortios_firewall_address6template

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
module "fortios_firewall_address6template" {
  source = "./modules/fortios/r/fortios_firewall_address6template"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ip6 - (required) is a type of string
  ip6 = null
  # name - (required) is a type of string
  name = null
  # subnet_segment_count - (required) is a type of number
  subnet_segment_count = null

  subnet_segment = [{
    bits      = null
    exclusive = null
    id        = null
    name      = null
    values = [{
      name  = null
      value = null
    }]
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

variable "ip6" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "subnet_segment_count" {
  description = "(required)"
  type        = number
}

variable "subnet_segment" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bits      = number
      exclusive = string
      id        = number
      name      = string
      values = list(object(
        {
          name  = string
          value = string
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
resource "fortios_firewall_address6template" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  ip6                   = var.ip6
  name                  = var.name
  subnet_segment_count  = var.subnet_segment_count

  dynamic "subnet_segment" {
    for_each = var.subnet_segment
    content {
      bits      = subnet_segment.value["bits"]
      exclusive = subnet_segment.value["exclusive"]
      id        = subnet_segment.value["id"]
      name      = subnet_segment.value["name"]

      dynamic "values" {
        for_each = subnet_segment.value.values
        content {
          name  = values.value["name"]
          value = values.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_address6template.this.id
}

output "this" {
  value = fortios_firewall_address6template.this
}
```

[top](#index)