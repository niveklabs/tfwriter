# oci_database_database

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_database" {
  source = "./modules/oci/d/oci_database_database"

  # database_id - (required) is a type of string
  database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_database" "this" {
  database_id = var.database_id
}
```

[top](#index)

### Outputs

```terraform
output "character_set" {
  description = "returns a string"
  value       = data.oci_database_database.this.character_set
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.compartment_id
}

output "connection_strings" {
  description = "returns a list of object"
  value       = data.oci_database_database.this.connection_strings
}

output "database" {
  description = "returns a list of object"
  value       = data.oci_database_database.this.database
}

output "database_software_image_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.database_software_image_id
}

output "db_backup_config" {
  description = "returns a list of object"
  value       = data.oci_database_database.this.db_backup_config
}

output "db_home_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.db_home_id
}

output "db_name" {
  description = "returns a string"
  value       = data.oci_database_database.this.db_name
}

output "db_system_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.db_system_id
}

output "db_unique_name" {
  description = "returns a string"
  value       = data.oci_database_database.this.db_unique_name
}

output "db_version" {
  description = "returns a string"
  value       = data.oci_database_database.this.db_version
}

output "db_workload" {
  description = "returns a string"
  value       = data.oci_database_database.this.db_workload
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_database.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_database.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.kms_key_id
}

output "kms_key_migration" {
  description = "returns a bool"
  value       = data.oci_database_database.this.kms_key_migration
}

output "kms_key_rotation" {
  description = "returns a number"
  value       = data.oci_database_database.this.kms_key_rotation
}

output "kms_key_version_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.kms_key_version_id
}

output "last_backup_timestamp" {
  description = "returns a string"
  value       = data.oci_database_database.this.last_backup_timestamp
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_database.this.lifecycle_details
}

output "ncharacter_set" {
  description = "returns a string"
  value       = data.oci_database_database.this.ncharacter_set
}

output "pdb_name" {
  description = "returns a string"
  value       = data.oci_database_database.this.pdb_name
}

output "source" {
  description = "returns a string"
  value       = data.oci_database_database.this.source
}

output "source_database_point_in_time_recovery_timestamp" {
  description = "returns a string"
  value       = data.oci_database_database.this.source_database_point_in_time_recovery_timestamp
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_database.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_database.this.time_created
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = data.oci_database_database.this.vm_cluster_id
}

output "this" {
  value = oci_database_database.this
}
```

[top](#index)