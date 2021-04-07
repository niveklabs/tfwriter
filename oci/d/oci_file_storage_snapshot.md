# oci_file_storage_snapshot

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
module "oci_file_storage_snapshot" {
  source = "./modules/oci/d/oci_file_storage_snapshot"

  # snapshot_id - (required) is a type of string
  snapshot_id = null
}
```

[top](#index)

### Variables

```terraform
variable "snapshot_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_file_storage_snapshot" "this" {
  # snapshot_id - (required) is a type of string
  snapshot_id = var.snapshot_id
}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_file_storage_snapshot.this.defined_tags
}

output "file_system_id" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.file_system_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_file_storage_snapshot.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.id
}

output "is_clone_source" {
  description = "returns a bool"
  value       = data.oci_file_storage_snapshot.this.is_clone_source
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.lifecycle_details
}

output "name" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.name
}

output "provenance_id" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.provenance_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_file_storage_snapshot.this.time_created
}

output "this" {
  value = oci_file_storage_snapshot.this
}
```

[top](#index)