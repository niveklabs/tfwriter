# fortios_dnsfilter_domainfilter

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
module "fortios_dnsfilter_domainfilter" {
  source = "./modules/fortios/r/fortios_dnsfilter_domainfilter"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (required) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null

  entries = [{
    action = null
    domain = null
    id     = null
    status = null
    type   = null
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
      action = string
      domain = string
      id     = number
      status = string
      type   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dnsfilter_domainfilter" "this" {
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
      # domain - (optional) is a type of string
      domain = entries.value["domain"]
      # id - (optional) is a type of number
      id = entries.value["id"]
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
  value       = fortios_dnsfilter_domainfilter.this.id
}

output "this" {
  value = fortios_dnsfilter_domainfilter.this
}
```

[top](#index)