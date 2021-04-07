# oci_core_cluster_network

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
module "oci_core_cluster_network" {
  source = "./modules/oci/d/oci_core_cluster_network"

  # cluster_network_id - (required) is a type of string
  cluster_network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_network_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_cluster_network" "this" {
  # cluster_network_id - (required) is a type of string
  cluster_network_id = var.cluster_network_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_cluster_network.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_cluster_network.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_cluster_network.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_cluster_network.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_cluster_network.this.id
}

output "instance_pools" {
  description = "returns a list of object"
  value       = data.oci_core_cluster_network.this.instance_pools
}

output "placement_configuration" {
  description = "returns a list of object"
  value       = data.oci_core_cluster_network.this.placement_configuration
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_cluster_network.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_cluster_network.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_core_cluster_network.this.time_updated
}

output "this" {
  value = oci_core_cluster_network.this
}
```

[top](#index)