# oci_dns_zones

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_zones" {
  source = "./modules/oci/d/oci_dns_zones"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # name - (optional) is a type of string
  name = null
  # name_contains - (optional) is a type of string
  name_contains = null
  # scope - (optional) is a type of string
  scope = null
  # sort_by - (optional) is a type of string
  sort_by = null
  # sort_order - (optional) is a type of string
  sort_order = null
  # state - (optional) is a type of string
  state = null
  # time_created_greater_than_or_equal_to - (optional) is a type of string
  time_created_greater_than_or_equal_to = null
  # time_created_less_than - (optional) is a type of string
  time_created_less_than = null
  # view_id - (optional) is a type of string
  view_id = null
  # zone_type - (optional) is a type of string
  zone_type = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_order" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_greater_than_or_equal_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_less_than" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "view_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_zones" "this" {
  compartment_id                        = var.compartment_id
  name                                  = var.name
  name_contains                         = var.name_contains
  scope                                 = var.scope
  sort_by                               = var.sort_by
  sort_order                            = var.sort_order
  state                                 = var.state
  time_created_greater_than_or_equal_to = var.time_created_greater_than_or_equal_to
  time_created_less_than                = var.time_created_less_than
  view_id                               = var.view_id
  zone_type                             = var.zone_type

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_dns_zones.this.id
}

output "zones" {
  description = "returns a list of object"
  value       = data.oci_dns_zones.this.zones
}

output "this" {
  value = oci_dns_zones.this
}
```

[top](#index)