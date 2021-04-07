# fortios_spamfilter_bwl

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
module "fortios_spamfilter_bwl" {
  source = "./modules/fortios/r/fortios_spamfilter_bwl"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null

  entries = [{
    action        = null
    addr_type     = null
    email_pattern = null
    id            = null
    ip4_subnet    = null
    ip6_subnet    = null
    pattern_type  = null
    status        = null
    type          = null
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
      action        = string
      addr_type     = string
      email_pattern = string
      id            = number
      ip4_subnet    = string
      ip6_subnet    = string
      pattern_type  = string
      status        = string
      type          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_spamfilter_bwl" "this" {
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
      # action - (optional) is a type of string
      action = entries.value["action"]
      # addr_type - (optional) is a type of string
      addr_type = entries.value["addr_type"]
      # email_pattern - (optional) is a type of string
      email_pattern = entries.value["email_pattern"]
      # id - (optional) is a type of number
      id = entries.value["id"]
      # ip4_subnet - (optional) is a type of string
      ip4_subnet = entries.value["ip4_subnet"]
      # ip6_subnet - (optional) is a type of string
      ip6_subnet = entries.value["ip6_subnet"]
      # pattern_type - (optional) is a type of string
      pattern_type = entries.value["pattern_type"]
      # status - (optional) is a type of string
      status = entries.value["status"]
      # type - (optional) is a type of string
      type = entries.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_bwl.this.id
}

output "this" {
  value = fortios_spamfilter_bwl.this
}
```

[top](#index)