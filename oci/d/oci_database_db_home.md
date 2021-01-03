# oci_database_db_home

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
module "oci_database_db_home" {
  source = "./modules/oci/d/oci_database_db_home"

  # db_home_id - (required) is a type of string
  db_home_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_home_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_db_home" "this" {
  db_home_id = var.db_home_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.compartment_id
}

output "database" {
  description = "returns a list of object"
  value       = data.oci_database_db_home.this.database
}

output "database_software_image_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.database_software_image_id
}

output "db_home_location" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.db_home_location
}

output "db_system_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.db_system_id
}

output "db_version" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.db_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_db_home.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_db_home.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.kms_key_id
}

output "kms_key_version_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.kms_key_version_id
}

output "last_patch_history_entry_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.last_patch_history_entry_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.lifecycle_details
}

output "source" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.source
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.time_created
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = data.oci_database_db_home.this.vm_cluster_id
}

output "this" {
  value = oci_database_db_home.this
}
```

[top](#index)