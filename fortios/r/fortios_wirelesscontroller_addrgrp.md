# fortios_wirelesscontroller_addrgrp

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
module "fortios_wirelesscontroller_addrgrp" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_addrgrp"

  # default_policy - (optional) is a type of string
  default_policy = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of string
  fosid = null

  addresses = [{
    id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_policy" {
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "addresses" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_addrgrp" "this" {
  default_policy        = var.default_policy
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid

  dynamic "addresses" {
    for_each = var.addresses
    content {
      id = addresses.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_policy" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_addrgrp.this.default_policy
}

output "fosid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_addrgrp.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_addrgrp.this.id
}

output "this" {
  value = fortios_wirelesscontroller_addrgrp.this
}
```

[top](#index)