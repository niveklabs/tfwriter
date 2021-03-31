# fortios_spamfilter_mheader

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
module "fortios_spamfilter_mheader" {
  source = "./modules/fortios/r/fortios_spamfilter_mheader"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null

  entries = [{
    action       = null
    fieldbody    = null
    fieldname    = null
    id           = null
    pattern_type = null
    status       = null
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
      action       = string
      fieldbody    = string
      fieldname    = string
      id           = number
      pattern_type = string
      status       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_spamfilter_mheader" "this" {
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid
  name                  = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      action       = entries.value["action"]
      fieldbody    = entries.value["fieldbody"]
      fieldname    = entries.value["fieldname"]
      id           = entries.value["id"]
      pattern_type = entries.value["pattern_type"]
      status       = entries.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_mheader.this.id
}

output "this" {
  value = fortios_spamfilter_mheader.this
}
```

[top](#index)