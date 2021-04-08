# vra_storage_profile_aws

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
module "vra_storage_profile_aws" {
  source = "./modules/vra/r/vra_storage_profile_aws"

  # default_item - (required) is a type of bool
  default_item = null
  # description - (optional) is a type of string
  description = null
  # device_type - (optional) is a type of string
  device_type = null
  # iops - (optional) is a type of string
  iops = null
  # name - (required) is a type of string
  name = null
  # region_id - (required) is a type of string
  region_id = null
  # supports_encryption - (optional) is a type of bool
  supports_encryption = null
  # volume_type - (optional) is a type of string
  volume_type = null

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
  description = "(required)"
  type        = bool
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iops" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region_id" {
  description = "(required)"
  type        = string
}

variable "supports_encryption" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "volume_type" {
  description = "(optional)"
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

### Resource

```terraform
resource "vra_storage_profile_aws" "this" {
  # default_item - (required) is a type of bool
  default_item = var.default_item
  # description - (optional) is a type of string
  description = var.description
  # device_type - (optional) is a type of string
  device_type = var.device_type
  # iops - (optional) is a type of string
  iops = var.iops
  # name - (required) is a type of string
  name = var.name
  # region_id - (required) is a type of string
  region_id = var.region_id
  # supports_encryption - (optional) is a type of bool
  supports_encryption = var.supports_encryption
  # volume_type - (optional) is a type of string
  volume_type = var.volume_type

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
  value       = vra_storage_profile_aws.this.created_at
}

output "description" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.description
}

output "device_type" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.device_type
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.id
}

output "iops" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.iops
}

output "links" {
  description = "returns a set of object"
  value       = vra_storage_profile_aws.this.links
}

output "organization_id" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.owner
}

output "supports_encryption" {
  description = "returns a bool"
  value       = vra_storage_profile_aws.this.supports_encryption
}

output "updated_at" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.updated_at
}

output "volume_type" {
  description = "returns a string"
  value       = vra_storage_profile_aws.this.volume_type
}

output "this" {
  value = vra_storage_profile_aws.this
}
```

[top](#index)