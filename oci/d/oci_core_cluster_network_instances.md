# oci_core_cluster_network_instances

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_cluster_network_instances" {
  source = "./modules/oci/d/oci_core_cluster_network_instances"

  # cluster_network_id - (required) is a type of string
  cluster_network_id = null
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
variable "cluster_network_id" {
  description = "(required)"
  type        = string
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
data "oci_core_cluster_network_instances" "this" {
  # cluster_network_id - (required) is a type of string
  cluster_network_id = var.cluster_network_id
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # display_name - (optional) is a type of string
  display_name = var.display_name

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
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
  value       = data.oci_core_cluster_network_instances.this.id
}

output "instances" {
  description = "returns a list of object"
  value       = data.oci_core_cluster_network_instances.this.instances
}

output "this" {
  value = oci_core_cluster_network_instances.this
}
```

[top](#index)