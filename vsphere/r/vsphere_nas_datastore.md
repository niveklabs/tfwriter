# vsphere_nas_datastore

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
module "vsphere_nas_datastore" {
  source = "./modules/vsphere/r/vsphere_nas_datastore"

  # access_mode - (optional) is a type of string
  access_mode = null
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # datastore_cluster_id - (optional) is a type of string
  datastore_cluster_id = null
  # folder - (optional) is a type of string
  folder = null
  # host_system_ids - (required) is a type of set of string
  host_system_ids = []
  # name - (required) is a type of string
  name = null
  # remote_hosts - (required) is a type of list of string
  remote_hosts = []
  # remote_path - (required) is a type of string
  remote_path = null
  # security_type - (optional) is a type of string
  security_type = null
  # tags - (optional) is a type of set of string
  tags = []
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "access_mode" {
  description = "(optional) - Access mode for the mount point. Can be one of readOnly or readWrite."
  type        = string
  default     = null
}

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

variable "folder" {
  description = "(optional) - The path to the datastore folder to put the datastore in."
  type        = string
  default     = null
}

variable "host_system_ids" {
  description = "(required) - The managed object IDs of the hosts to mount the datastore on."
  type        = set(string)
}

variable "name" {
  description = "(required) - The name of the datastore."
  type        = string
}

variable "remote_hosts" {
  description = "(required) - The hostnames or IP addresses of the remote server or servers. Only one element should be present for NFS v3 but multiple can be present for NFS v4.1."
  type        = list(string)
}

variable "remote_path" {
  description = "(required) - The remote path of the mount point."
  type        = string
}

variable "security_type" {
  description = "(optional) - The security type to use."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(optional) - The type of NAS volume. Can be one of NFS (to denote v3) or NFS41 (to denote NFS v4.1)."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_nas_datastore" "this" {
  # access_mode - (optional) is a type of string
  access_mode = var.access_mode
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = var.custom_attributes
  # datastore_cluster_id - (optional) is a type of string
  datastore_cluster_id = var.datastore_cluster_id
  # folder - (optional) is a type of string
  folder = var.folder
  # host_system_ids - (required) is a type of set of string
  host_system_ids = var.host_system_ids
  # name - (required) is a type of string
  name = var.name
  # remote_hosts - (required) is a type of list of string
  remote_hosts = var.remote_hosts
  # remote_path - (required) is a type of string
  remote_path = var.remote_path
  # security_type - (optional) is a type of string
  security_type = var.security_type
  # tags - (optional) is a type of set of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "accessible" {
  description = "returns a bool"
  value       = vsphere_nas_datastore.this.accessible
}

output "capacity" {
  description = "returns a number"
  value       = vsphere_nas_datastore.this.capacity
}

output "free_space" {
  description = "returns a number"
  value       = vsphere_nas_datastore.this.free_space
}

output "id" {
  description = "returns a string"
  value       = vsphere_nas_datastore.this.id
}

output "maintenance_mode" {
  description = "returns a string"
  value       = vsphere_nas_datastore.this.maintenance_mode
}

output "multiple_host_access" {
  description = "returns a bool"
  value       = vsphere_nas_datastore.this.multiple_host_access
}

output "protocol_endpoint" {
  description = "returns a string"
  value       = vsphere_nas_datastore.this.protocol_endpoint
}

output "uncommitted_space" {
  description = "returns a number"
  value       = vsphere_nas_datastore.this.uncommitted_space
}

output "url" {
  description = "returns a string"
  value       = vsphere_nas_datastore.this.url
}

output "this" {
  value = vsphere_nas_datastore.this
}
```

[top](#index)