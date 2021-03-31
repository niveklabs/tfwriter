# fortios_wirelesscontrollerhotspot20_anqp3gppcellular

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
module "fortios_wirelesscontrollerhotspot20_anqp3gppcellular" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqp3gppcellular"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  mcc_mnc_list = [{
    id  = null
    mcc = null
    mnc = null
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

variable "mcc_mnc_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id  = number
      mcc = string
      mnc = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_anqp3gppcellular" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "mcc_mnc_list" {
    for_each = var.mcc_mnc_list
    content {
      id  = mcc_mnc_list.value["id"]
      mcc = mcc_mnc_list.value["mcc"]
      mnc = mcc_mnc_list.value["mnc"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqp3gppcellular.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqp3gppcellular.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_anqp3gppcellular.this
}
```

[top](#index)