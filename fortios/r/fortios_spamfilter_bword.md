# fortios_spamfilter_bword

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
module "fortios_spamfilter_bword" {
  source = "./modules/fortios/r/fortios_spamfilter_bword"

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
    id           = null
    language     = null
    pattern      = null
    pattern_type = null
    score        = null
    status       = null
    where        = null
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
      id           = number
      language     = string
      pattern      = string
      pattern_type = string
      score        = number
      status       = string
      where        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_spamfilter_bword" "this" {
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
      # id - (optional) is a type of number
      id = entries.value["id"]
      # language - (optional) is a type of string
      language = entries.value["language"]
      # pattern - (optional) is a type of string
      pattern = entries.value["pattern"]
      # pattern_type - (optional) is a type of string
      pattern_type = entries.value["pattern_type"]
      # score - (optional) is a type of number
      score = entries.value["score"]
      # status - (optional) is a type of string
      status = entries.value["status"]
      # where - (optional) is a type of string
      where = entries.value["where"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_spamfilter_bword.this.id
}

output "this" {
  value = fortios_spamfilter_bword.this
}
```

[top](#index)