# oci_core_public_ip_pools

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_public_ip_pools" {
  source = "./modules/oci/d/oci_core_public_ip_pools"

  # byoip_range_id - (optional) is a type of string
  byoip_range_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null

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
variable "byoip_range_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
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
data "oci_core_public_ip_pools" "this" {
  byoip_range_id = var.byoip_range_id
  compartment_id = var.compartment_id
  display_name   = var.display_name

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
  value       = data.oci_core_public_ip_pools.this.id
}

output "public_ip_pool_collection" {
  description = "returns a list of object"
  value       = data.oci_core_public_ip_pools.this.public_ip_pool_collection
}

output "this" {
  value = oci_core_public_ip_pools.this
}
```

[top](#index)