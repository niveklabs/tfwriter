# fortios_emailfilter_mheader

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
module "fortios_emailfilter_mheader" {
  source = "./modules/fortios/r/fortios_emailfilter_mheader"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
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
resource "fortios_emailfilter_mheader" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # name - (optional) is a type of string
  name = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      # action - (optional) is a type of string
      action = entries.value["action"]
      # fieldbody - (optional) is a type of string
      fieldbody = entries.value["fieldbody"]
      # fieldname - (optional) is a type of string
      fieldname = entries.value["fieldname"]
      # id - (optional) is a type of number
      id = entries.value["id"]
      # pattern_type - (optional) is a type of string
      pattern_type = entries.value["pattern_type"]
      # status - (optional) is a type of string
      status = entries.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_emailfilter_mheader.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_emailfilter_mheader.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_emailfilter_mheader.this.name
}

output "this" {
  value = fortios_emailfilter_mheader.this
}
```

[top](#index)