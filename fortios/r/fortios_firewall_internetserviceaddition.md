# fortios_firewall_internetserviceaddition

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
module "fortios_firewall_internetserviceaddition" {
  source = "./modules/fortios/r/fortios_firewall_internetserviceaddition"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null

  entry = [{
    id = null
    port_range = [{
      end_port   = null
      id         = null
      start_port = null
    }]
    protocol = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "entry" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
      port_range = list(object(
        {
          end_port   = number
          id         = number
          start_port = number
        }
      ))
      protocol = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetserviceaddition" "this" {
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid

  dynamic "entry" {
    for_each = var.entry
    content {
      id       = entry.value["id"]
      protocol = entry.value["protocol"]

      dynamic "port_range" {
        for_each = entry.value.port_range
        content {
          end_port   = port_range.value["end_port"]
          id         = port_range.value["id"]
          start_port = port_range.value["start_port"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_internetserviceaddition.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetserviceaddition.this.id
}

output "this" {
  value = fortios_firewall_internetserviceaddition.this
}
```

[top](#index)