# vra_storage_profile_azure

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
module "vra_storage_profile_azure" {
  source = "./modules/vra/r/vra_storage_profile_azure"

  # data_disk_caching - (optional) is a type of string
  data_disk_caching = null
  # default_item - (required) is a type of bool
  default_item = null
  # description - (optional) is a type of string
  description = null
  # disk_type - (optional) is a type of string
  disk_type = null
  # name - (required) is a type of string
  name = null
  # os_disk_caching - (optional) is a type of string
  os_disk_caching = null
  # region_id - (required) is a type of string
  region_id = null
  # storage_account_id - (optional) is a type of string
  storage_account_id = null
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
variable "data_disk_caching" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_item" {
  description = "(required)"
  type        = bool
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "os_disk_caching" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_id" {
  description = "(required)"
  type        = string
}

variable "storage_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "supports_encryption" {
  description = "(optional)"
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
resource "vra_storage_profile_azure" "this" {
  # data_disk_caching - (optional) is a type of string
  data_disk_caching = var.data_disk_caching
  # default_item - (required) is a type of bool
  default_item = var.default_item
  # description - (optional) is a type of string
  description = var.description
  # disk_type - (optional) is a type of string
  disk_type = var.disk_type
  # name - (required) is a type of string
  name = var.name
  # os_disk_caching - (optional) is a type of string
  os_disk_caching = var.os_disk_caching
  # region_id - (required) is a type of string
  region_id = var.region_id
  # storage_account_id - (optional) is a type of string
  storage_account_id = var.storage_account_id
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
output "created_at" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.created_at
}

output "data_disk_caching" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.data_disk_caching
}

output "description" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.description
}

output "disk_type" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.disk_type
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_storage_profile_azure.this.links
}

output "organization_id" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.organization_id
}

output "os_disk_caching" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.os_disk_caching
}

output "owner" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.owner
}

output "storage_account_id" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.storage_account_id
}

output "supports_encryption" {
  description = "returns a bool"
  value       = vra_storage_profile_azure.this.supports_encryption
}

output "updated_at" {
  description = "returns a string"
  value       = vra_storage_profile_azure.this.updated_at
}

output "this" {
  value = vra_storage_profile_azure.this
}
```

[top](#index)