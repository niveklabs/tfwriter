# oci_database_autonomous_database_backup

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
module "oci_database_autonomous_database_backup" {
  source = "./modules/oci/d/oci_database_autonomous_database_backup"

  # autonomous_database_backup_id - (required) is a type of string
  autonomous_database_backup_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_database_backup_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_database_backup" "this" {
  # autonomous_database_backup_id - (required) is a type of string
  autonomous_database_backup_id = var.autonomous_database_backup_id
}
```

[top](#index)

### Outputs

```terraform
output "autonomous_database_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.autonomous_database_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.compartment_id
}

output "database_size_in_tbs" {
  description = "returns a number"
  value       = data.oci_database_autonomous_database_backup.this.database_size_in_tbs
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.id
}

output "is_automatic" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database_backup.this.is_automatic
}

output "is_restorable" {
  description = "returns a bool"
  value       = data.oci_database_autonomous_database_backup.this.is_restorable
}

output "key_store_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.key_store_id
}

output "key_store_wallet_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.key_store_wallet_name
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.state
}

output "time_ended" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.time_ended
}

output "time_started" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.time_started
}

output "type" {
  description = "returns a string"
  value       = data.oci_database_autonomous_database_backup.this.type
}

output "this" {
  value = oci_database_autonomous_database_backup.this
}
```

[top](#index)