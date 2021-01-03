# opc_compute_storage_volume_snapshot

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_storage_volume_snapshot" {
  source = "./modules/opc/r/opc_compute_storage_volume_snapshot"

  # collocated - (optional) is a type of bool
  collocated = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # parent_volume_bootable - (optional) is a type of bool
  parent_volume_bootable = null
  # tags - (optional) is a type of list of string
  tags = []
  # volume_name - (required) is a type of string
  volume_name = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "collocated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_volume_bootable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "volume_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_storage_volume_snapshot" "this" {
  collocated             = var.collocated
  description            = var.description
  name                   = var.name
  parent_volume_bootable = var.parent_volume_bootable
  tags                   = var.tags
  volume_name            = var.volume_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.account
}

output "id" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.id
}

output "machine_image_name" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.machine_image_name
}

output "name" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.name
}

output "platform" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.platform
}

output "property" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.property
}

output "size" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.size
}

output "snapshot_id" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.snapshot_id
}

output "snapshot_timestamp" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.snapshot_timestamp
}

output "start_timestamp" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.start_timestamp
}

output "status" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.status
}

output "status_detail" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.status_detail
}

output "status_timestamp" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.status_timestamp
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_storage_volume_snapshot.this.uri
}

output "this" {
  value = opc_compute_storage_volume_snapshot.this
}
```

[top](#index)