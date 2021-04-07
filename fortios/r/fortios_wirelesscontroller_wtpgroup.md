# fortios_wirelesscontroller_wtpgroup

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
module "fortios_wirelesscontroller_wtpgroup" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_wtpgroup"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # platform_type - (optional) is a type of string
  platform_type = null

  wtps = [{
    wtp_id = null
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

variable "platform_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wtps" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      wtp_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_wtpgroup" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # platform_type - (optional) is a type of string
  platform_type = var.platform_type

  dynamic "wtps" {
    for_each = var.wtps
    content {
      # wtp_id - (optional) is a type of string
      wtp_id = wtps.value["wtp_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpgroup.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpgroup.this.name
}

output "platform_type" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_wtpgroup.this.platform_type
}

output "this" {
  value = fortios_wirelesscontroller_wtpgroup.this
}
```

[top](#index)