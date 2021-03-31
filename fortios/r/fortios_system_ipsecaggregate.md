# fortios_system_ipsecaggregate

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
module "fortios_system_ipsecaggregate" {
  source = "./modules/fortios/r/fortios_system_ipsecaggregate"

  # algorithm - (optional) is a type of string
  algorithm = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  member = [{
    tunnel_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "member" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      tunnel_name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ipsecaggregate" "this" {
  algorithm             = var.algorithm
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "member" {
    for_each = var.member
    content {
      tunnel_name = member.value["tunnel_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = fortios_system_ipsecaggregate.this.algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ipsecaggregate.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_ipsecaggregate.this.name
}

output "this" {
  value = fortios_system_ipsecaggregate.this
}
```

[top](#index)