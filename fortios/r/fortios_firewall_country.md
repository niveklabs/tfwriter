# fortios_firewall_country

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
module "fortios_firewall_country" {
  source = "./modules/fortios/r/fortios_firewall_country"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null

  region = [{
    id = null
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

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_country" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # name - (optional) is a type of string
  name = var.name

  dynamic "region" {
    for_each = var.region
    content {
      # id - (optional) is a type of number
      id = region.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_country.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_country.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_country.this.name
}

output "this" {
  value = fortios_firewall_country.this
}
```

[top](#index)