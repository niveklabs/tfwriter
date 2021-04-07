# fortios_emailfilter_dnsbl

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
module "fortios_emailfilter_dnsbl" {
  source = "./modules/fortios/r/fortios_emailfilter_dnsbl"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null

  entries = [{
    action = null
    id     = null
    server = null
    status = null
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
      action = string
      id     = number
      server = string
      status = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_emailfilter_dnsbl" "this" {
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
      # id - (optional) is a type of number
      id = entries.value["id"]
      # server - (optional) is a type of string
      server = entries.value["server"]
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
  value       = fortios_emailfilter_dnsbl.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_emailfilter_dnsbl.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_emailfilter_dnsbl.this.name
}

output "this" {
  value = fortios_emailfilter_dnsbl.this
}
```

[top](#index)