# oci_database_db_node

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
module "oci_database_db_node" {
  source = "./modules/oci/d/oci_database_db_node"

  # db_node_id - (required) is a type of string
  db_node_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_node_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_db_node" "this" {
  db_node_id = var.db_node_id
}
```

[top](#index)

### Outputs

```terraform
output "additional_details" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.additional_details
}

output "backup_vnic_id" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.backup_vnic_id
}

output "db_system_id" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.db_system_id
}

output "fault_domain" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.fault_domain
}

output "hostname" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.id
}

output "maintenance_type" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.maintenance_type
}

output "software_storage_size_in_gb" {
  description = "returns a number"
  value       = data.oci_database_db_node.this.software_storage_size_in_gb
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.time_created
}

output "time_maintenance_window_end" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.time_maintenance_window_end
}

output "time_maintenance_window_start" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.time_maintenance_window_start
}

output "vnic_id" {
  description = "returns a string"
  value       = data.oci_database_db_node.this.vnic_id
}

output "this" {
  value = oci_database_db_node.this
}
```

[top](#index)