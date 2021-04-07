# oci_database_autonomous_container_database

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
module "oci_database_autonomous_container_database" {
  source = "./modules/oci/d/oci_database_autonomous_container_database"

  # autonomous_container_database_id - (required) is a type of string
  autonomous_container_database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_container_database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_container_database" "this" {
  autonomous_container_database_id = var.autonomous_container_database_id
}
```

[top](#index)

### Outputs

```terraform
output "autonomous_exadata_infrastructure_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.autonomous_exadata_infrastructure_id
}

output "autonomous_vm_cluster_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.autonomous_vm_cluster_id
}

output "availability_domain" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.availability_domain
}

output "backup_config" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_container_database.this.backup_config
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.compartment_id
}

output "db_unique_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.db_unique_name
}

output "db_version" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.db_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_container_database.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_container_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.id
}

output "infrastructure_type" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.infrastructure_type
}

output "key_store_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.key_store_id
}

output "key_store_wallet_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.key_store_wallet_name
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.kms_key_id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.last_maintenance_run_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.lifecycle_details
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_container_database.this.maintenance_window
}

output "maintenance_window_details" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_container_database.this.maintenance_window_details
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.next_maintenance_run_id
}

output "patch_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.patch_id
}

output "patch_model" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.patch_model
}

output "peer_autonomous_container_database_backup_config" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_container_database.this.peer_autonomous_container_database_backup_config
}

output "peer_autonomous_container_database_compartment_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.peer_autonomous_container_database_compartment_id
}

output "peer_autonomous_container_database_display_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.peer_autonomous_container_database_display_name
}

output "peer_autonomous_exadata_infrastructure_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.peer_autonomous_exadata_infrastructure_id
}

output "peer_autonomous_vm_cluster_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.peer_autonomous_vm_cluster_id
}

output "peer_db_unique_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.peer_db_unique_name
}

output "protection_mode" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.protection_mode
}

output "role" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.role
}

output "rotate_key_trigger" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_container_database.this.rotate_key_trigger
}

output "service_level_agreement_type" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.service_level_agreement_type
}

output "standby_maintenance_buffer_in_days" {
  description = "returns a number"
  value       = data.oci_database_autonomous_container_database.this.standby_maintenance_buffer_in_days
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.time_created
}

output "vault_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database.this.vault_id
}

output "this" {
  value = oci_database_autonomous_container_database.this
}
```

[top](#index)