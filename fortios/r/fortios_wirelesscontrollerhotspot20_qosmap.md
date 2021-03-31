# fortios_wirelesscontrollerhotspot20_qosmap

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
module "fortios_wirelesscontrollerhotspot20_qosmap" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_qosmap"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  dscp_except = [{
    dscp  = null
    index = null
    up    = null
  }]

  dscp_range = [{
    high  = null
    index = null
    low   = null
    up    = null
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

variable "dscp_except" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dscp  = number
      index = number
      up    = number
    }
  ))
  default = []
}

variable "dscp_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      high  = number
      index = number
      low   = number
      up    = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_qosmap" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "dscp_except" {
    for_each = var.dscp_except
    content {
      dscp  = dscp_except.value["dscp"]
      index = dscp_except.value["index"]
      up    = dscp_except.value["up"]
    }
  }

  dynamic "dscp_range" {
    for_each = var.dscp_range
    content {
      high  = dscp_range.value["high"]
      index = dscp_range.value["index"]
      low   = dscp_range.value["low"]
      up    = dscp_range.value["up"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_qosmap.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_qosmap.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_qosmap.this
}
```

[top](#index)