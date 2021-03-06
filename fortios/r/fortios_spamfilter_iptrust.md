# fortios_spamfilter_iptrust

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
module "fortios_spamfilter_iptrust" {
  source = "./modules/fortios/r/fortios_spamfilter_iptrust"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
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
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "fortios_spamfilter_iptrust" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fosid - (required) is a type of number
  fosid = var.fosid
  # name - (required) is a type of string
  name = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      # addr_type - (optional) is a type of string
      addr_type = entries.value["addr_type"]
      # id - (optional) is a type of number
      id = entries.value["id"]
      # ip4_subnet - (optional) is a type of string
      ip4_subnet = entries.value["ip4_subnet"]
      # ip6_subnet - (optional) is a type of string
      ip6_subnet = entries.value["ip6_subnet"]
      # status - (optional) is a type of string
      status = entries.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_iptrust.this.id
}

output "this" {
  value = fortios_spamfilter_iptrust.this
}
```

[top](#index)