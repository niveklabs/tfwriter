# alicloud_disk

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_disk" {
  source = "./modules/alicloud/r/alicloud_disk"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # category - (optional) is a type of string
  category = null
  # delete_auto_snapshot - (optional) is a type of bool
  delete_auto_snapshot = null
  # delete_with_instance - (optional) is a type of bool
  delete_with_instance = null
  # description - (optional) is a type of string
  description = null
  # enable_auto_snapshot - (optional) is a type of bool
  enable_auto_snapshot = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (optional) is a type of string
  name = null
  # performance_level - (optional) is a type of string
  performance_level = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # size - (required) is a type of number
  size = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required)"
  type        = string
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_auto_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "delete_with_instance" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_auto_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "performance_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_disk" "this" {
  availability_zone    = var.availability_zone
  category             = var.category
  delete_auto_snapshot = var.delete_auto_snapshot
  delete_with_instance = var.delete_with_instance
  description          = var.description
  enable_auto_snapshot = var.enable_auto_snapshot
  encrypted            = var.encrypted
  kms_key_id           = var.kms_key_id
  name                 = var.name
  performance_level    = var.performance_level
  resource_group_id    = var.resource_group_id
  size                 = var.size
  snapshot_id          = var.snapshot_id
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_disk.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_disk.this.status
}

output "this" {
  value = alicloud_disk.this
}
```

[top](#index)