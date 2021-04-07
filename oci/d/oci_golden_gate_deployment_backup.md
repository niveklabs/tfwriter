# oci_golden_gate_deployment_backup

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
module "oci_golden_gate_deployment_backup" {
  source = "./modules/oci/d/oci_golden_gate_deployment_backup"

  # deployment_backup_id - (required) is a type of string
  deployment_backup_id = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_backup_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_golden_gate_deployment_backup" "this" {
  # deployment_backup_id - (required) is a type of string
  deployment_backup_id = var.deployment_backup_id
}
```

[top](#index)

### Outputs

```terraform
output "backup_type" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.backup_type
}

output "bucket" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.bucket
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_deployment_backup.this.defined_tags
}

output "deployment_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.deployment_id
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_deployment_backup.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.id
}

output "is_automatic" {
  description = "returns a bool"
  value       = data.oci_golden_gate_deployment_backup.this.is_automatic
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.lifecycle_details
}

output "namespace" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.namespace
}

output "object" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.object
}

output "ogg_version" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.ogg_version
}

output "state" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_deployment_backup.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.time_created
}

output "time_of_backup" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.time_of_backup
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment_backup.this.time_updated
}

output "this" {
  value = oci_golden_gate_deployment_backup.this
}
```

[top](#index)