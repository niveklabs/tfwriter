# fortios_wirelesscontrollerhotspot20_anqpvenuename

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
module "fortios_wirelesscontrollerhotspot20_anqpvenuename" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqpvenuename"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  value_list = [{
    index = null
    lang  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      index = number
      lang  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_anqpvenuename" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "value_list" {
    for_each = var.value_list
    content {
      # index - (optional) is a type of number
      index = value_list.value["index"]
      # lang - (optional) is a type of string
      lang = value_list.value["lang"]
      # value - (optional) is a type of string
      value = value_list.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpvenuename.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpvenuename.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_anqpvenuename.this
}
```

[top](#index)