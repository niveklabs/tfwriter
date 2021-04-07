# oci_database_maintenance_run

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
module "oci_database_maintenance_run" {
  source = "./modules/oci/d/oci_database_maintenance_run"

  # maintenance_run_id - (required) is a type of string
  maintenance_run_id = null
}
```

[top](#index)

### Variables

```terraform
variable "maintenance_run_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_maintenance_run" "this" {
  # maintenance_run_id - (required) is a type of string
  maintenance_run_id = var.maintenance_run_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_database_maintenance_run.this.is_enabled
}

output "is_patch_now_enabled" {
  description = "returns a bool"
  value       = data.oci_database_maintenance_run.this.is_patch_now_enabled
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.lifecycle_details
}

output "maintenance_subtype" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.maintenance_subtype
}

output "maintenance_type" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.maintenance_type
}

output "patch_id" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.patch_id
}

output "peer_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.peer_maintenance_run_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.state
}

output "target_resource_id" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.target_resource_id
}

output "target_resource_type" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.target_resource_type
}

output "time_ended" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.time_ended
}

output "time_scheduled" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.time_scheduled
}

output "time_started" {
  description = "returns a string"
  value       = data.oci_database_maintenance_run.this.time_started
}

output "this" {
  value = oci_database_maintenance_run.this
}
```

[top](#index)