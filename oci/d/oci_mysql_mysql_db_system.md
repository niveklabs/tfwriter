# oci_mysql_mysql_db_system

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
module "oci_mysql_mysql_db_system" {
  source = "./modules/oci/d/oci_mysql_mysql_db_system"

  # db_system_id - (required) is a type of string
  db_system_id = null
}
```

[top](#index)

### Variables

```terraform
variable "db_system_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_mysql_mysql_db_system" "this" {
  db_system_id = var.db_system_id
}
```

[top](#index)

### Outputs

```terraform
output "admin_password" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.admin_password
  sensitive   = true
}

output "admin_username" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.admin_username
}

output "analytics_cluster" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.analytics_cluster
}

output "availability_domain" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.availability_domain
}

output "backup_policy" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.backup_policy
}

output "channels" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.channels
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.compartment_id
}

output "configuration_id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.configuration_id
}

output "data_storage_size_in_gb" {
  description = "returns a number"
  value       = data.oci_mysql_mysql_db_system.this.data_storage_size_in_gb
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_mysql_mysql_db_system.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.display_name
}

output "endpoints" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.endpoints
}

output "fault_domain" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.fault_domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_mysql_mysql_db_system.this.freeform_tags
}

output "heat_wave_cluster" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.heat_wave_cluster
}

output "hostname_label" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.hostname_label
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.ip_address
}

output "is_analytics_cluster_attached" {
  description = "returns a bool"
  value       = data.oci_mysql_mysql_db_system.this.is_analytics_cluster_attached
}

output "is_heat_wave_cluster_attached" {
  description = "returns a bool"
  value       = data.oci_mysql_mysql_db_system.this.is_heat_wave_cluster_attached
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.lifecycle_details
}

output "maintenance" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.maintenance
}

output "mysql_version" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.mysql_version
}

output "port" {
  description = "returns a number"
  value       = data.oci_mysql_mysql_db_system.this.port
}

output "port_x" {
  description = "returns a number"
  value       = data.oci_mysql_mysql_db_system.this.port_x
}

output "shape_name" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.shape_name
}

output "shutdown_type" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.shutdown_type
}

output "source" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_system.this.source
}

output "state" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_system.this.time_updated
}

output "this" {
  value = oci_mysql_mysql_db_system.this
}
```

[top](#index)