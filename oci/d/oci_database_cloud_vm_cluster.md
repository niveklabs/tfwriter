# oci_database_cloud_vm_cluster

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
module "oci_database_cloud_vm_cluster" {
  source = "./modules/oci/d/oci_database_cloud_vm_cluster"

  # cloud_vm_cluster_id - (required) is a type of string
  cloud_vm_cluster_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cloud_vm_cluster_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_cloud_vm_cluster" "this" {
  cloud_vm_cluster_id = var.cloud_vm_cluster_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.availability_domain
}

output "backup_network_nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_database_cloud_vm_cluster.this.backup_network_nsg_ids
}

output "backup_subnet_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.backup_subnet_id
}

output "cloud_exadata_infrastructure_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.cloud_exadata_infrastructure_id
}

output "cluster_name" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.cluster_name
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.compartment_id
}

output "cpu_core_count" {
  description = "returns a number"
  value       = data.oci_database_cloud_vm_cluster.this.cpu_core_count
}

output "data_storage_percentage" {
  description = "returns a number"
  value       = data.oci_database_cloud_vm_cluster.this.data_storage_percentage
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_cloud_vm_cluster.this.defined_tags
}

output "disk_redundancy" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.disk_redundancy
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_cloud_vm_cluster.this.freeform_tags
}

output "gi_version" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.gi_version
}

output "hostname" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.id
}

output "iorm_config_cache" {
  description = "returns a list of object"
  value       = data.oci_database_cloud_vm_cluster.this.iorm_config_cache
}

output "is_local_backup_enabled" {
  description = "returns a bool"
  value       = data.oci_database_cloud_vm_cluster.this.is_local_backup_enabled
}

output "is_sparse_diskgroup_enabled" {
  description = "returns a bool"
  value       = data.oci_database_cloud_vm_cluster.this.is_sparse_diskgroup_enabled
}

output "last_update_history_entry_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.last_update_history_entry_id
}

output "license_model" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.lifecycle_details
}

output "listener_port" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.listener_port
}

output "node_count" {
  description = "returns a number"
  value       = data.oci_database_cloud_vm_cluster.this.node_count
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_database_cloud_vm_cluster.this.nsg_ids
}

output "scan_dns_name" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.scan_dns_name
}

output "scan_dns_record_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.scan_dns_record_id
}

output "scan_ip_ids" {
  description = "returns a list of string"
  value       = data.oci_database_cloud_vm_cluster.this.scan_ip_ids
}

output "shape" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.shape
}

output "ssh_public_keys" {
  description = "returns a list of string"
  value       = data.oci_database_cloud_vm_cluster.this.ssh_public_keys
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.state
}

output "storage_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_cloud_vm_cluster.this.storage_size_in_gbs
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.subnet_id
}

output "system_version" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.system_version
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.time_zone
}

output "vip_ids" {
  description = "returns a list of string"
  value       = data.oci_database_cloud_vm_cluster.this.vip_ids
}

output "zone_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_vm_cluster.this.zone_id
}

output "this" {
  value = oci_database_cloud_vm_cluster.this
}
```

[top](#index)