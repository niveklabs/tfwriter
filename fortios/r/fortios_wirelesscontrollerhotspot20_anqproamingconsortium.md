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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontrollerhotspot20_anqproamingconsortium" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqproamingconsortium"

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
  name = var.name

  dynamic "oi_list" {
    for_each = var.oi_list
    content {
      comment = oi_list.value["comment"]
      index   = oi_list.value["index"]
      oi      = oi_list.value["oi"]
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