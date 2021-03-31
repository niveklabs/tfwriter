# oci_core_local_peering_gateways

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
module "oci_core_local_peering_gateways" {
  source = "./modules/oci/d/oci_core_local_peering_gateways"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # vcn_id - (optional) is a type of string
  vcn_id = null

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

variable "vcn_id" {
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
data "oci_core_local_peering_gateways" "this" {
  compartment_id = var.compartment_id
  vcn_id         = var.vcn_id

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
  value       = data.oci_core_local_peering_gateways.this.id
}

output "local_peering_gateways" {
  description = "returns a list of object"
  value       = data.oci_core_local_peering_gateways.this.local_peering_gateways
}

output "this" {
  value = oci_core_local_peering_gateways.this
}
```

[top](#index)