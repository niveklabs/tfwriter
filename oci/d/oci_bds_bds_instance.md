# oci_bds_bds_instance

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
module "oci_bds_bds_instance" {
  source = "./modules/oci/d/oci_bds_bds_instance"

  # bds_instance_id - (required) is a type of string
  bds_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bds_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_bds_bds_instance" "this" {
  # bds_instance_id - (required) is a type of string
  bds_instance_id = var.bds_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "cloud_sql_details" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.cloud_sql_details
}

output "cluster_admin_password" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.cluster_admin_password
  sensitive   = true
}

output "cluster_details" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.cluster_details
}

output "cluster_public_key" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.cluster_public_key
}

output "cluster_version" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.cluster_version
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_bds_bds_instance.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_bds_bds_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.id
}

output "is_cloud_sql_configured" {
  description = "returns a bool"
  value       = data.oci_bds_bds_instance.this.is_cloud_sql_configured
}

output "is_high_availability" {
  description = "returns a bool"
  value       = data.oci_bds_bds_instance.this.is_high_availability
}

output "is_secure" {
  description = "returns a bool"
  value       = data.oci_bds_bds_instance.this.is_secure
}

output "master_node" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.master_node
}

output "network_config" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.network_config
}

output "nodes" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.nodes
}

output "number_of_nodes" {
  description = "returns a number"
  value       = data.oci_bds_bds_instance.this.number_of_nodes
}

output "state" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_bds_bds_instance.this.time_updated
}

output "util_node" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.util_node
}

output "worker_node" {
  description = "returns a list of object"
  value       = data.oci_bds_bds_instance.this.worker_node
}

output "this" {
  value = oci_bds_bds_instance.this
}
```

[top](#index)