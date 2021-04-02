# oci_database_vm_cluster

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_vm_cluster" {
  source = "./modules/oci/d/oci_database_vm_cluster"

  # vm_cluster_id - (required) is a type of string
  vm_cluster_id = null
}
```

[top](#index)

### Variables

```terraform
variable "vm_cluster_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_vm_cluster" "this" {
  vm_cluster_id = var.vm_cluster_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.compartment_id
}

output "cpu_core_count" {
  description = "returns a number"
  value       = data.oci_database_vm_cluster.this.cpu_core_count
}

output "cpus_enabled" {
  description = "returns a number"
  value       = data.oci_database_vm_cluster.this.cpus_enabled
}

output "data_storage_size_in_tbs" {
  description = "returns a number"
  value       = data.oci_database_vm_cluster.this.data_storage_size_in_tbs
}

output "db_node_storage_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_vm_cluster.this.db_node_storage_size_in_gbs
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_vm_cluster.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.display_name
}

output "exadata_infrastructure_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.exadata_infrastructure_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_vm_cluster.this.freeform_tags
}

output "gi_version" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.gi_version
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.id
}

output "is_local_backup_enabled" {
  description = "returns a bool"
  value       = data.oci_database_vm_cluster.this.is_local_backup_enabled
}

output "is_sparse_diskgroup_enabled" {
  description = "returns a bool"
  value       = data.oci_database_vm_cluster.this.is_sparse_diskgroup_enabled
}

output "last_patch_history_entry_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.last_patch_history_entry_id
}

output "license_model" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.lifecycle_details
}

output "memory_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_vm_cluster.this.memory_size_in_gbs
}

output "shape" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.shape
}

output "ssh_public_keys" {
  description = "returns a list of string"
  value       = data.oci_database_vm_cluster.this.ssh_public_keys
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.time_zone
}

output "vm_cluster_network_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster.this.vm_cluster_network_id
}

output "this" {
  value = oci_database_vm_cluster.this
}
```

[top](#index)