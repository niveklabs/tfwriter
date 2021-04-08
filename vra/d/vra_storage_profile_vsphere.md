# vra_storage_profile_vsphere

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/vra/d/vra_storage_profile_vsphere"

  # filter - (optional) is a type of string
  filter = null
  # shares_level - (optional) is a type of string
  shares_level = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shares_level" {
  description = "(optional) - Indicates whether this storage profile supports encryption or not."
  type        = string
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

### Datasource

```terraform
data "vra_storage_profile_vsphere" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
  # shares_level - (optional) is a type of string
  shares_level = var.shares_level

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
  value       = data.vra_storage_profile_vsphere.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.created_at
}

output "default_item" {
  description = "returns a bool"
  value       = data.vra_storage_profile_vsphere.this.default_item
}

output "description" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.description
}

output "disk_mode" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.disk_mode
}

output "disk_type" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.disk_type
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.id
}

output "limit_iops" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.limit_iops
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_storage_profile_vsphere.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.owner
}

output "provisioning_type" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.provisioning_type
}

output "shares" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.shares
}

output "supports_encryption" {
  description = "returns a bool"
  value       = data.vra_storage_profile_vsphere.this.supports_encryption
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_storage_profile_vsphere.this.updated_at
}

output "this" {
  value = vra_storage_profile_vsphere.this
}
```

[top](#index)