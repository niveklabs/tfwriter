# oci_containerengine_node_pools

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
module "oci_containerengine_node_pools" {
  source = "./modules/oci/d/oci_containerengine_node_pools"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # name - (optional) is a type of string
  name = null

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
variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "name" {
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
data "oci_containerengine_node_pools" "this" {
  cluster_id     = var.cluster_id
  compartment_id = var.compartment_id
  name           = var.name

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
  value       = data.oci_containerengine_node_pools.this.id
}

output "node_pools" {
  description = "returns a list of object"
  value       = data.oci_containerengine_node_pools.this.node_pools
}

output "this" {
  value = oci_containerengine_node_pools.this
}
```

[top](#index)