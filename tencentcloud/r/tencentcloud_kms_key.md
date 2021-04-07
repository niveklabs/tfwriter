# tencentcloud_kms_key

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_kms_key" {
  source = "./modules/tencentcloud/r/tencentcloud_kms_key"

  # alias - (required) is a type of string
  alias = null
  # description - (optional) is a type of string
  description = null
  # is_archived - (optional) is a type of bool
  is_archived = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # key_rotation_enabled - (optional) is a type of bool
  key_rotation_enabled = null
  # key_usage - (optional) is a type of string
  key_usage = null
  # pending_delete_window_in_days - (optional) is a type of number
  pending_delete_window_in_days = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "alias" {
  description = "(required) - Name of CMK. The name can only contain English letters, numbers, underscore and hyphen '-'. The first character must be a letter or number."
  type        = string
}

variable "description" {
  description = "(optional) - Description of CMK. The maximum is 1024 bytes."
  type        = string
  default     = null
}

variable "is_archived" {
  description = "(optional) - Specify whether to archive key. Default value is `false`. This field is conflict with `is_enabled`, valid when key_state is `Enabled`, `Disabled`, `Archived`."
  type        = bool
  default     = null
}

variable "is_enabled" {
  description = "(optional) - Specify whether to enable key. Default value is `false`. This field is conflict with `is_archived`, valid when key_state is `Enabled`, `Disabled`, `Archived`."
  type        = bool
  default     = null
}

variable "key_rotation_enabled" {
  description = "(optional) - Specify whether to enable key rotation, valid when key_usage is `ENCRYPT_DECRYPT`. Default value is `false`."
  type        = bool
  default     = null
}

variable "key_usage" {
  description = "(optional) - Usage of CMK. Available values include `ENCRYPT_DECRYPT`, `ASYMMETRIC_DECRYPT_RSA_2048`, `ASYMMETRIC_DECRYPT_SM2`, `ASYMMETRIC_SIGN_VERIFY_SM2`, `ASYMMETRIC_SIGN_VERIFY_RSA_2048`, `ASYMMETRIC_SIGN_VERIFY_ECC`. Default value is `ENCRYPT_DECRYPT`."
  type        = string
  default     = null
}

variable "pending_delete_window_in_days" {
  description = "(optional) - Duration in days after which the key is deleted after destruction of the resource, must be between 7 and 30 days. Defaults to 7 days."
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of CMK."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kms_key" "this" {
  # alias - (required) is a type of string
  alias = var.alias
  # description - (optional) is a type of string
  description = var.description
  # is_archived - (optional) is a type of bool
  is_archived = var.is_archived
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # key_rotation_enabled - (optional) is a type of bool
  key_rotation_enabled = var.key_rotation_enabled
  # key_usage - (optional) is a type of string
  key_usage = var.key_usage
  # pending_delete_window_in_days - (optional) is a type of number
  pending_delete_window_in_days = var.pending_delete_window_in_days
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_kms_key.this.id
}

output "key_state" {
  description = "returns a string"
  value       = tencentcloud_kms_key.this.key_state
}

output "this" {
  value = tencentcloud_kms_key.this
}
```

[top](#index)