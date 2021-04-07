# opc_compute_storage_volume

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
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_storage_volume" {
  source = "./modules/opc/r/opc_compute_storage_volume"

  # bootable - (optional) is a type of bool
  bootable = null
  # description - (optional) is a type of string
  description = null
  # hypervisor - (optional) is a type of string
  hypervisor = null
  # image_list - (optional) is a type of string
  image_list = null
  # image_list_entry - (optional) is a type of number
  image_list_entry = null
  # machine_image - (optional) is a type of string
  machine_image = null
  # managed - (optional) is a type of bool
  managed = null
  # name - (required) is a type of string
  name = null
  # platform - (optional) is a type of string
  platform = null
  # readonly - (optional) is a type of bool
  readonly = null
  # size - (required) is a type of number
  size = null
  # snapshot - (optional) is a type of string
  snapshot = null
  # snapshot_account - (optional) is a type of string
  snapshot_account = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # status - (optional) is a type of string
  status = null
  # storage_pool - (optional) is a type of string
  storage_pool = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # tags - (optional) is a type of list of string
  tags = []
  # uri - (optional) is a type of string
  uri = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bootable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hypervisor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_list_entry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "machine_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "managed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "readonly" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "snapshot" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_storage_volume" "this" {
  # bootable - (optional) is a type of bool
  bootable = var.bootable
  # description - (optional) is a type of string
  description = var.description
  # hypervisor - (optional) is a type of string
  hypervisor = var.hypervisor
  # image_list - (optional) is a type of string
  image_list = var.image_list
  # image_list_entry - (optional) is a type of number
  image_list_entry = var.image_list_entry
  # machine_image - (optional) is a type of string
  machine_image = var.machine_image
  # managed - (optional) is a type of bool
  managed = var.managed
  # name - (required) is a type of string
  name = var.name
  # platform - (optional) is a type of string
  platform = var.platform
  # readonly - (optional) is a type of bool
  readonly = var.readonly
  # size - (required) is a type of number
  size = var.size
  # snapshot - (optional) is a type of string
  snapshot = var.snapshot
  # snapshot_account - (optional) is a type of string
  snapshot_account = var.snapshot_account
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # status - (optional) is a type of string
  status = var.status
  # storage_pool - (optional) is a type of string
  storage_pool = var.storage_pool
  # storage_type - (optional) is a type of string
  storage_type = var.storage_type
  # tags - (optional) is a type of list of string
  tags = var.tags
  # uri - (optional) is a type of string
  uri = var.uri

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "hypervisor" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.id
}

output "machine_image" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.machine_image
}

output "managed" {
  description = "returns a bool"
  value       = opc_compute_storage_volume.this.managed
}

output "platform" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.platform
}

output "readonly" {
  description = "returns a bool"
  value       = opc_compute_storage_volume.this.readonly
}

output "snapshot" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.snapshot
}

output "snapshot_account" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.snapshot_account
}

output "snapshot_id" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.snapshot_id
}

output "status" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.status
}

output "storage_pool" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.storage_pool
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_storage_volume.this.uri
}

output "this" {
  value = opc_compute_storage_volume.this
}
```

[top](#index)