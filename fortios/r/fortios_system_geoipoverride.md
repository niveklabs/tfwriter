# fortios_system_geoipoverride

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
module "fortios_system_geoipoverride" {
  source = "./modules/fortios/r/fortios_system_geoipoverride"

  # country_id - (optional) is a type of string
  country_id = null
  # description - (optional) is a type of string
  description = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  ip6_range = [{
    end_ip   = null
    id       = null
    start_ip = null
  }]

  ip_range = [{
    end_ip   = null
    id       = null
    start_ip = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "country_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
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
  description = "(required)"
  type        = string
}

variable "ip6_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end_ip   = string
      id       = number
      start_ip = string
    }
  ))
  default = []
}

variable "ip_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end_ip   = string
      id       = number
      start_ip = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_geoipoverride" "this" {
  country_id            = var.country_id
  description           = var.description
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "ip6_range" {
    for_each = var.ip6_range
    content {
      end_ip   = ip6_range.value["end_ip"]
      id       = ip6_range.value["id"]
      start_ip = ip6_range.value["start_ip"]
    }
  }

  dynamic "ip_range" {
    for_each = var.ip_range
    content {
      end_ip   = ip_range.value["end_ip"]
      id       = ip_range.value["id"]
      start_ip = ip_range.value["start_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "country_id" {
  description = "returns a string"
  value       = fortios_system_geoipoverride.this.country_id
}

output "description" {
  description = "returns a string"
  value       = fortios_system_geoipoverride.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_system_geoipoverride.this.id
}

output "this" {
  value = fortios_system_geoipoverride.this
}
```

[top](#index)