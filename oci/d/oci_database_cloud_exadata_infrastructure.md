# oci_database_cloud_exadata_infrastructure

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_cloud_exadata_infrastructure" {
  source = "./modules/oci/d/oci_database_cloud_exadata_infrastructure"

  # cloud_exadata_infrastructure_id - (required) is a type of string
  cloud_exadata_infrastructure_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cloud_exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_cloud_exadata_infrastructure" "this" {
  cloud_exadata_infrastructure_id = var.cloud_exadata_infrastructure_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.availability_domain
}

output "available_storage_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_cloud_exadata_infrastructure.this.available_storage_size_in_gbs
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.compartment_id
}

output "compute_count" {
  description = "returns a number"
  value       = data.oci_database_cloud_exadata_infrastructure.this.compute_count
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.last_maintenance_run_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.lifecycle_details
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = data.oci_database_cloud_exadata_infrastructure.this.maintenance_window
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.next_maintenance_run_id
}

output "shape" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.shape
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.state
}

output "storage_count" {
  description = "returns a number"
  value       = data.oci_database_cloud_exadata_infrastructure.this.storage_count
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_cloud_exadata_infrastructure.this.time_created
}

output "total_storage_size_in_gbs" {
  description = "returns a number"
  value       = data.oci_database_cloud_exadata_infrastructure.this.total_storage_size_in_gbs
}

output "this" {
  value = oci_database_cloud_exadata_infrastructure.this
}
```

[top](#index)