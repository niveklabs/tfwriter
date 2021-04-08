# vra_storage_profile_vsphere

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_storage_profile_vsphere" {
  source = "./modules/vra/r/vra_storage_profile_vsphere"

  # datastore_id - (optional) is a type of string
  datastore_id = null
  # default_item - (required) is a type of bool
  default_item = null
  # description - (optional) is a type of string
  description = null
  # disk_mode - (optional) is a type of string
  disk_mode = null
  # disk_type - (optional) is a type of string
  disk_type = null
  # limit_iops - (optional) is a type of string
  limit_iops = null
  # name - (required) is a type of string
  name = null
  # provisioning_type - (optional) is a type of string
  provisioning_type = null
  # region_id - (required) is a type of string
  region_id = null
  # shares - (optional) is a type of string
  shares = null
  # shares_level - (optional) is a type of string
  shares_level = null
  # storage_policy_id - (optional) is a type of string
  storage_policy_id = null
  # supports_encryption - (optional) is a type of bool
  supports_encryption = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "datastore_id" {
  description = "(optional) - Id of the vSphere Datastore for placing disk and VM."
  type        = string
  default     = null
}

variable "default_item" {
  description = "(required) - Indicates if a storage profile acts as a default storage profile for a disk."
  type        = bool
}

variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "disk_mode" {
  description = "(optional) - Type of mode for the disk. Omitting this value will set it to dependent. example: dependent / independent-persistent / independent-nonpersistent."
  type        = string
  default     = null
}

variable "disk_type" {
  description = "(optional) - Disk types are specified as standard or first class, empty value is considered as standard."
  type        = string
  default     = null
}

variable "limit_iops" {
  description = "(optional) - The upper bound for the I/O operations per second allocated for each virtual disk."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - A human-friendly name used as an identifier in APIs that support this option."
  type        = string
}

variable "provisioning_type" {
  description = "(optional) - Type of provisioning policy for the disk."
  type        = string
  default     = null
}

variable "region_id" {
  description = "(required) - The Id of the region that is associated with the storage profile."
  type        = string
}

variable "shares" {
  description = "(optional) - A specific number of shares assigned to each virtual machine."
  type        = string
  default     = null
}

variable "shares_level" {
  description = "(optional) - Indicates whether this storage profile supports encryption or not."
  type        = string
  default     = null
}

variable "storage_policy_id" {
  description = "(optional) - Id of the vSphere Storage Policy to be applied."
  type        = string
  default     = null
}

variable "supports_encryption" {
  description = "(optional) - Indicates whether this storage profile supports encryption or not."
  type        = bool
  default     = null
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_storage_profile_vsphere" "this" {
  # datastore_id - (optional) is a type of string
  datastore_id = var.datastore_id
  # default_item - (required) is a type of bool
  default_item = var.default_item
  # description - (optional) is a type of string
  description = var.description
  # disk_mode - (optional) is a type of string
  disk_mode = var.disk_mode
  # disk_type - (optional) is a type of string
  disk_type = var.disk_type
  # limit_iops - (optional) is a type of string
  limit_iops = var.limit_iops
  # name - (required) is a type of string
  name = var.name
  # provisioning_type - (optional) is a type of string
  provisioning_type = var.provisioning_type
  # region_id - (required) is a type of string
  region_id = var.region_id
  # shares - (optional) is a type of string
  shares = var.shares
  # shares_level - (optional) is a type of string
  shares_level = var.shares_level
  # storage_policy_id - (optional) is a type of string
  storage_policy_id = var.storage_policy_id
  # supports_encryption - (optional) is a type of bool
  supports_encryption = var.supports_encryption

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_account_id" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.created_at
}

output "disk_mode" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.disk_mode
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_storage_profile_vsphere.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_storage_profile_vsphere.this.updated_at
}

output "this" {
  value = vra_storage_profile_vsphere.this
}
```

[top](#index)