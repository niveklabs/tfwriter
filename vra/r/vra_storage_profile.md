# vra_storage_profile

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
module "vra_storage_profile" {
  source = "./modules/vra/r/vra_storage_profile"

  # default_item - (required) is a type of bool
  default_item = null
  # description - (optional) is a type of string
  description = null
  # disk_properties - (optional) is a type of map of string
  disk_properties = {}
  # disk_target_properties - (optional) is a type of map of string
  disk_target_properties = {}
  # name - (required) is a type of string
  name = null
  # region_id - (required) is a type of string
  region_id = null
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
variable "default_item" {
  description = "(required) - Indicates if this storage profile is a default profile."
  type        = bool
}

variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "disk_properties" {
  description = "(optional) - Map of storage properties that are to be applied on disk while provisioning."
  type        = map(string)
  default     = null
}

variable "disk_target_properties" {
  description = "(optional) - Map of storage placements to know where the disk is provisioned."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - A human-friendly name for storage profile."
  type        = string
}

variable "region_id" {
  description = "(required) - The id of the region that is associated with the storage profile."
  type        = string
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
resource "vra_storage_profile" "this" {
  # default_item - (required) is a type of bool
  default_item = var.default_item
  # description - (optional) is a type of string
  description = var.description
  # disk_properties - (optional) is a type of map of string
  disk_properties = var.disk_properties
  # disk_target_properties - (optional) is a type of map of string
  disk_target_properties = var.disk_target_properties
  # name - (required) is a type of string
  name = var.name
  # region_id - (required) is a type of string
  region_id = var.region_id
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
  value       = vra_storage_profile.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = vra_storage_profile.this.created_at
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_storage_profile.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_storage_profile.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_storage_profile.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_storage_profile.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_storage_profile.this.owner
}

output "supports_encryption" {
  description = "returns a bool"
  value       = vra_storage_profile.this.supports_encryption
}

output "updated_at" {
  description = "returns a string"
  value       = vra_storage_profile.this.updated_at
}

output "this" {
  value = vra_storage_profile.this
}
```

[top](#index)