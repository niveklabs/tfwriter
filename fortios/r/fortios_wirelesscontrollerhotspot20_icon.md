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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontrollerhotspot20_icon" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_icon"

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
  name = var.name

  dynamic "icon_list" {
    for_each = var.icon_list
    content {
      file   = icon_list.value["file"]
      height = icon_list.value["height"]
      lang   = icon_list.value["lang"]
      name   = icon_list.value["name"]
      type   = icon_list.value["type"]
      width  = icon_list.value["width"]
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