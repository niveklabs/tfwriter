# oci_core_byoip_allocated_ranges

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
module "oci_core_byoip_allocated_ranges" {
  source = "./modules/oci/d/oci_core_byoip_allocated_ranges"

  # byoip_range_id - (required) is a type of string
  byoip_range_id = null

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
  description = "(required)"
  type        = string
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
data "oci_core_byoip_allocated_ranges" "this" {
  byoip_range_id = var.byoip_range_id

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
output "byoip_allocated_range_collection" {
  description = "returns a list of object"
  value       = data.oci_core_byoip_allocated_ranges.this.byoip_allocated_range_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_byoip_allocated_ranges.this.id
}

output "this" {
  value = oci_core_byoip_allocated_ranges.this
}
```

[top](#index)