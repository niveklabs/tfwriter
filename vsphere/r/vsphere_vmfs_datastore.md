# vsphere_vmfs_datastore

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_vmfs_datastore" {
  source = "./modules/vsphere/r/vsphere_vmfs_datastore"

  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # datastore_cluster_id - (optional) is a type of string
  datastore_cluster_id = null
  # disks - (required) is a type of list of string
  disks = []
  # folder - (optional) is a type of string
  folder = null
  # host_system_id - (required) is a type of string
  host_system_id = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "datastore_cluster_id" {
  description = "(optional) - The managed object ID of the datastore cluster to place the datastore in."
  type        = string
  default     = null
}

variable "disks" {
  description = "(required) - The disks to add to the datastore."
  type        = list(string)
}

variable "folder" {
  description = "(optional) - The path to the datastore folder to put the datastore in."
  type        = string
  default     = null
}

variable "host_system_id" {
  description = "(required) - The managed object ID of the host to set up the datastore on."
  type        = string
}

variable "name" {
  description = "(required) - The name of the datastore."
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_vmfs_datastore" "this" {
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = var.custom_attributes
  # datastore_cluster_id - (optional) is a type of string
  datastore_cluster_id = var.datastore_cluster_id
  # disks - (required) is a type of list of string
  disks = var.disks
  # folder - (optional) is a type of string
  folder = var.folder
  # host_system_id - (required) is a type of string
  host_system_id = var.host_system_id
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "accessible" {
  description = "returns a bool"
  value       = vsphere_vmfs_datastore.this.accessible
}

output "capacity" {
  description = "returns a number"
  value       = vsphere_vmfs_datastore.this.capacity
}

output "free_space" {
  description = "returns a number"
  value       = vsphere_vmfs_datastore.this.free_space
}

output "id" {
  description = "returns a string"
  value       = vsphere_vmfs_datastore.this.id
}

output "maintenance_mode" {
  description = "returns a string"
  value       = vsphere_vmfs_datastore.this.maintenance_mode
}

output "multiple_host_access" {
  description = "returns a bool"
  value       = vsphere_vmfs_datastore.this.multiple_host_access
}

output "uncommitted_space" {
  description = "returns a number"
  value       = vsphere_vmfs_datastore.this.uncommitted_space
}

output "url" {
  description = "returns a string"
  value       = vsphere_vmfs_datastore.this.url
}

output "this" {
  value = vsphere_vmfs_datastore.this
}
```

[top](#index)