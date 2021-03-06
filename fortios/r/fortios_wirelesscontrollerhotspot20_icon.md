# fortios_wirelesscontrollerhotspot20_icon

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
module "fortios_wirelesscontrollerhotspot20_icon" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_icon"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  icon_list = [{
    file   = null
    height = null
    lang   = null
    name   = null
    type   = null
    width  = null
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

variable "icon_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      file   = string
      height = number
      lang   = string
      name   = string
      type   = string
      width  = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_icon" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "icon_list" {
    for_each = var.icon_list
    content {
      # file - (optional) is a type of string
      file = icon_list.value["file"]
      # height - (optional) is a type of number
      height = icon_list.value["height"]
      # lang - (optional) is a type of string
      lang = icon_list.value["lang"]
      # name - (optional) is a type of string
      name = icon_list.value["name"]
      # type - (optional) is a type of string
      type = icon_list.value["type"]
      # width - (optional) is a type of number
      width = icon_list.value["width"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_icon.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_icon.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_icon.this
}
```

[top](#index)