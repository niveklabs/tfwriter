# alicloud_kms_key

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_key" {
  source = "./modules/alicloud/r/alicloud_kms_key"

  # automatic_rotation - (optional) is a type of string
  automatic_rotation = null
  # deletion_window_in_days - (optional) is a type of number
  deletion_window_in_days = null
  # description - (optional) is a type of string
  description = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # key_spec - (optional) is a type of string
  key_spec = null
  # key_state - (optional) is a type of string
  key_state = null
  # key_usage - (optional) is a type of string
  key_usage = null
  # origin - (optional) is a type of string
  origin = null
  # pending_window_in_days - (optional) is a type of number
  pending_window_in_days = null
  # protection_level - (optional) is a type of string
  protection_level = null
  # rotation_interval - (optional) is a type of string
  rotation_interval = null
}
```

[top](#index)

### Variables

```terraform
variable "automatic_rotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_window_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_usage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pending_window_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protection_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rotation_interval" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kms_key" "this" {
  # automatic_rotation - (optional) is a type of string
  automatic_rotation = var.automatic_rotation
  # deletion_window_in_days - (optional) is a type of number
  deletion_window_in_days = var.deletion_window_in_days
  # description - (optional) is a type of string
  description = var.description
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # key_spec - (optional) is a type of string
  key_spec = var.key_spec
  # key_state - (optional) is a type of string
  key_state = var.key_state
  # key_usage - (optional) is a type of string
  key_usage = var.key_usage
  # origin - (optional) is a type of string
  origin = var.origin
  # pending_window_in_days - (optional) is a type of number
  pending_window_in_days = var.pending_window_in_days
  # protection_level - (optional) is a type of string
  protection_level = var.protection_level
  # rotation_interval - (optional) is a type of string
  rotation_interval = var.rotation_interval
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = alicloud_kms_key.this.arn
}

output "creation_date" {
  description = "returns a string"
  value       = alicloud_kms_key.this.creation_date
}

output "creator" {
  description = "returns a string"
  value       = alicloud_kms_key.this.creator
}

output "delete_date" {
  description = "returns a string"
  value       = alicloud_kms_key.this.delete_date
}

output "id" {
  description = "returns a string"
  value       = alicloud_kms_key.this.id
}

output "key_spec" {
  description = "returns a string"
  value       = alicloud_kms_key.this.key_spec
}

output "last_rotation_date" {
  description = "returns a string"
  value       = alicloud_kms_key.this.last_rotation_date
}

output "material_expire_time" {
  description = "returns a string"
  value       = alicloud_kms_key.this.material_expire_time
}

output "next_rotation_date" {
  description = "returns a string"
  value       = alicloud_kms_key.this.next_rotation_date
}

output "primary_key_version" {
  description = "returns a string"
  value       = alicloud_kms_key.this.primary_key_version
}

output "this" {
  value = alicloud_kms_key.this
}
```

[top](#index)