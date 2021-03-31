# fortios_emailfilter_iptrust

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
module "fortios_emailfilter_iptrust" {
  source = "./modules/fortios/r/fortios_emailfilter_iptrust"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null

  entries = [{
    addr_type  = null
    id         = null
    ip4_subnet = null
    ip6_subnet = null
    status     = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr_type  = string
      id         = number
      ip4_subnet = string
      ip6_subnet = string
      status     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_emailfilter_iptrust" "this" {
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid
  name                  = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      addr_type  = entries.value["addr_type"]
      id         = entries.value["id"]
      ip4_subnet = entries.value["ip4_subnet"]
      ip6_subnet = entries.value["ip6_subnet"]
      status     = entries.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_emailfilter_iptrust.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_emailfilter_iptrust.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_emailfilter_iptrust.this.name
}

output "this" {
  value = fortios_emailfilter_iptrust.this
}
```

[top](#index)