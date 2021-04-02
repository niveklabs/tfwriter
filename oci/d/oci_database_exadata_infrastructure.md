# oci_database_exadata_infrastructure

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
module "oci_database_exadata_infrastructure" {
  source = "./modules/oci/d/oci_database_exadata_infrastructure"

  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = null
}
```

[top](#index)

### Variables

```terraform
variable "exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_exadata_infrastructure" "this" {
  exadata_infrastructure_id = var.exadata_infrastructure_id
}
```

[top](#index)

### Outputs

```terraform
output "activation_file" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.activation_file
}

output "admin_network_cidr" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.admin_network_cidr
}

output "cloud_control_plane_server1" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.cloud_control_plane_server1
}

output "cloud_control_plane_server2" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.cloud_control_plane_server2
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.compartment_id
}

output "contacts" {
  description = "returns a list of object"
  value       = data.oci_database_exadata_infrastructure.this.contacts
}

output "corporate_proxy" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.corporate_proxy
}

output "cpus_enabled" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.cpus_enabled
}

output "csi_number" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.csi_number
}

output "data_storage_size_in_tbs" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.data_storage_size_in_tbs
}

output "db_node_storage_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.db_node_storage_size_in_gbs
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_exadata_infrastructure.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.display_name
}

output "dns_server" {
  description = "returns a list of string"
  value       = data.oci_database_exadata_infrastructure.this.dns_server
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_exadata_infrastructure.this.freeform_tags
}

output "gateway" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.id
}

output "infini_band_network_cidr" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.infini_band_network_cidr
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.lifecycle_details
}

output "maintenance_slo_status" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.maintenance_slo_status
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = data.oci_database_exadata_infrastructure.this.maintenance_window
}

output "max_cpu_count" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.max_cpu_count
}

output "max_data_storage_in_tbs" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.max_data_storage_in_tbs
}

output "max_db_node_storage_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.max_db_node_storage_in_gbs
}

output "max_memory_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.max_memory_in_gbs
}

output "memory_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_exadata_infrastructure.this.memory_size_in_gbs
}

output "netmask" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.netmask
}

output "ntp_server" {
  description = "returns a list of string"
  value       = data.oci_database_exadata_infrastructure.this.ntp_server
}

output "shape" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.shape
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = data.oci_database_exadata_infrastructure.this.time_zone
}

output "this" {
  value = oci_database_exadata_infrastructure.this
}
```

[top](#index)