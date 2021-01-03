# oci_database_database_upgrade_history_entry

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
module "oci_database_database_upgrade_history_entry" {
  source = "./modules/oci/d/oci_database_database_upgrade_history_entry"

  # database_id - (required) is a type of string
  database_id = null
  # upgrade_history_entry_id - (required) is a type of string
  upgrade_history_entry_id = null
}
```

[top](#index)

### Variables

```terraform
variable "database_id" {
  description = "(required)"
  type        = string
}

variable "upgrade_history_entry_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_database_upgrade_history_entry" "this" {
  database_id              = var.database_id
  upgrade_history_entry_id = var.upgrade_history_entry_id
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.action
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.lifecycle_details
}

output "source" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.source
}

output "source_db_home_id" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.source_db_home_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.state
}

output "target_database_software_image_id" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.target_database_software_image_id
}

output "target_db_home_id" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.target_db_home_id
}

output "target_db_version" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.target_db_version
}

output "time_ended" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.time_ended
}

output "time_started" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entry.this.time_started
}

output "this" {
  value = oci_database_database_upgrade_history_entry.this
}
```

[top](#index)