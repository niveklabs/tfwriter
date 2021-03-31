# opc_compute_storage_volume_snapshot

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_storage_volume_snapshot" {
  source = "./modules/opc/d/opc_compute_storage_volume_snapshot"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opc_compute_storage_volume_snapshot" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.account
}

output "collocated" {
  description = "returns a bool"
  value       = data.opc_compute_storage_volume_snapshot.this.collocated
}

output "description" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.description
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.id
}

output "machine_image_name" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.machine_image_name
}

output "parent_volume_bootable" {
  description = "returns a bool"
  value       = data.opc_compute_storage_volume_snapshot.this.parent_volume_bootable
}

output "platform" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.platform
}

output "property" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.property
}

output "size" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.size
}

output "snapshot_id" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.snapshot_id
}

output "snapshot_timestamp" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.snapshot_timestamp
}

output "start_timestamp" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.start_timestamp
}

output "status" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.status
}

output "status_detail" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.status_detail
}

output "status_timestamp" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.status_timestamp
}

output "tags" {
  description = "returns a list of string"
  value       = data.opc_compute_storage_volume_snapshot.this.tags
}

output "uri" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.uri
}

output "volume_name" {
  description = "returns a string"
  value       = data.opc_compute_storage_volume_snapshot.this.volume_name
}

output "this" {
  value = opc_compute_storage_volume_snapshot.this
}
```

[top](#index)