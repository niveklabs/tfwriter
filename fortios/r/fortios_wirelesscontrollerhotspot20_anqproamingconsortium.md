# fortios_wirelesscontrollerhotspot20_anqproamingconsortium

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
module "fortios_wirelesscontrollerhotspot20_anqproamingconsortium" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqproamingconsortium"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  oi_list = [{
    comment = null
    index   = null
    oi      = null
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

variable "oi_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment = string
      index   = number
      oi      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_anqproamingconsortium" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "oi_list" {
    for_each = var.oi_list
    content {
      # comment - (optional) is a type of string
      comment = oi_list.value["comment"]
      # index - (optional) is a type of number
      index = oi_list.value["index"]
      # oi - (optional) is a type of string
      oi = oi_list.value["oi"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqproamingconsortium.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqproamingconsortium.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_anqproamingconsortium.this
}
```

[top](#index)