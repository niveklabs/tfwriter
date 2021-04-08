# vra_storage_profile

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
module "vra_storage_profile" {
  source = "./modules/vra/d/vra_storage_profile"

  # description - (optional) is a type of string
  description = null
  # disk_properties - (optional) is a type of map of string
  disk_properties = {}
  # filter - (optional) is a type of string
  filter = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "filter" {
  description = "(optional) - Search criteria to filter the list of storage profiles."
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
data "vra_storage_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # disk_properties - (optional) is a type of map of string
  disk_properties = var.disk_properties
  # filter - (optional) is a type of string
  filter = var.filter

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
  value       = data.vra_storage_profile.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.created_at
}

output "default_item" {
  description = "returns a bool"
  value       = data.vra_storage_profile.this.default_item
}

output "disk_properties" {
  description = "returns a map of string"
  value       = data.vra_storage_profile.this.disk_properties
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_storage_profile.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.owner
}

output "supports_encryption" {
  description = "returns a bool"
  value       = data.vra_storage_profile.this.supports_encryption
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_storage_profile.this.updated_at
}

output "this" {
  value = vra_storage_profile.this
}
```

[top](#index)