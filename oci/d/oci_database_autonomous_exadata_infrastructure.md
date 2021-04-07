# oci_database_autonomous_exadata_infrastructure

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
module "oci_database_autonomous_exadata_infrastructure" {
  source = "./modules/oci/d/oci_database_autonomous_exadata_infrastructure"

  # autonomous_exadata_infrastructure_id - (required) is a type of string
  autonomous_exadata_infrastructure_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_exadata_infrastructure" "this" {
  # autonomous_exadata_infrastructure_id - (required) is a type of string
  autonomous_exadata_infrastructure_id = var.autonomous_exadata_infrastructure_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.freeform_tags
}

output "hostname" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.id
}

output "last_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.last_maintenance_run_id
}

output "license_model" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.lifecycle_details
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.maintenance_window
}

output "maintenance_window_details" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.maintenance_window_details
}

output "next_maintenance_run_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.next_maintenance_run_id
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.nsg_ids
}

output "scan_dns_name" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.scan_dns_name
}

output "shape" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.shape
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.time_created
}

output "zone_id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure.this.zone_id
}

output "this" {
  value = oci_database_autonomous_exadata_infrastructure.this
}
```

[top](#index)