# fortios_wirelesscontrollerhotspot20_h2qpoperatorname

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
module "fortios_wirelesscontrollerhotspot20_h2qpoperatorname" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_h2qpoperatorname"

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
resource "fortios_wirelesscontrollerhotspot20_h2qpoperatorname" "this" {
  name = var.name

  dynamic "value_list" {
    for_each = var.value_list
    content {
      index = value_list.value["index"]
      lang  = value_list.value["lang"]
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
  value       = fortios_wirelesscontrollerhotspot20_h2qpoperatorname.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpoperatorname.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_h2qpoperatorname.this
}
```

[top](#index)