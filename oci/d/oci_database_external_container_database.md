# oci_database_external_container_database

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
module "oci_database_external_container_database" {
  source = "./modules/oci/d/oci_database_external_container_database"

  # external_container_database_id - (required) is a type of string
  external_container_database_id = null
}
```

[top](#index)

### Variables

```terraform
variable "external_container_database_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_external_container_database" "this" {
  external_container_database_id = var.external_container_database_id
}
```

[top](#index)

### Outputs

```terraform
output "character_set" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.character_set
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.compartment_id
}

output "database_edition" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.database_edition
}

output "database_management_config" {
  description = "returns a list of object"
  value       = data.oci_database_external_container_database.this.database_management_config
}

output "database_version" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.database_version
}

output "db_id" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.db_id
}

output "db_packs" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.db_packs
}

output "db_unique_name" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.db_unique_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_external_container_database.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_external_container_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.lifecycle_details
}

output "ncharacter_set" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.ncharacter_set
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = data.oci_database_external_container_database.this.time_zone
}

output "this" {
  value = oci_database_external_container_database.this
}
```

[top](#index)