# fortios_dlp_filepattern

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
module "fortios_dlp_filepattern" {
  source = "./modules/fortios/r/fortios_dlp_filepattern"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null

  entries = [{
    file_type   = null
    filter_type = null
    pattern     = null
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
      file_type   = string
      filter_type = string
      pattern     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dlp_filepattern" "this" {
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid
  name                  = var.name

  dynamic "entries" {
    for_each = var.entries
    content {
      file_type   = entries.value["file_type"]
      filter_type = entries.value["filter_type"]
      pattern     = entries.value["pattern"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_dlp_filepattern.this.id
}

output "this" {
  value = fortios_dlp_filepattern.this
}
```

[top](#index)