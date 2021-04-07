# tencentcloud_kms_external_key

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
module "tencentcloud_kms_external_key" {
  source = "./modules/tencentcloud/r/tencentcloud_kms_external_key"

  # alias - (required) is a type of string
  alias = null
  # description - (optional) is a type of string
  description = null
  # is_archived - (optional) is a type of bool
  is_archived = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # key_material_base64 - (optional) is a type of string
  key_material_base64 = null
  # pending_delete_window_in_days - (optional) is a type of number
  pending_delete_window_in_days = null
  # tags - (optional) is a type of map of string
  tags = {}
  # valid_to - (optional) is a type of number
  valid_to = null
  # wrapping_algorithm - (optional) is a type of string
  wrapping_algorithm = null
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

variable "key_material_base64" {
  description = "(optional) - The base64-encoded key material encrypted with the public_key. For regions using the national secret version, the length of the imported key material is required to be 128 bits, and for regions using the FIPS version, the length of the imported key material is required to be 256 bits."
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

variable "valid_to" {
  description = "(optional) - This value means the effective timestamp of the key material, 0 means it does not expire. Need to be greater than the current timestamp, the maximum support is 2147443200."
  type        = number
  default     = null
}

variable "wrapping_algorithm" {
  description = "(optional) - The algorithm for encrypting key material. Available values include `RSAES_PKCS1_V1_5`, `RSAES_OAEP_SHA_1` and `RSAES_OAEP_SHA_256`. Default value is `RSAES_PKCS1_V1_5`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kms_external_key" "this" {
  # alias - (required) is a type of string
  alias = var.alias
  # description - (optional) is a type of string
  description = var.description
  # is_archived - (optional) is a type of bool
  is_archived = var.is_archived
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # key_material_base64 - (optional) is a type of string
  key_material_base64 = var.key_material_base64
  # pending_delete_window_in_days - (optional) is a type of number
  pending_delete_window_in_days = var.pending_delete_window_in_days
  # tags - (optional) is a type of map of string
  tags = var.tags
  # valid_to - (optional) is a type of number
  valid_to = var.valid_to
  # wrapping_algorithm - (optional) is a type of string
  wrapping_algorithm = var.wrapping_algorithm
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_kms_external_key.this.id
}

output "key_state" {
  description = "returns a string"
  value       = tencentcloud_kms_external_key.this.key_state
}

output "this" {
  value = tencentcloud_kms_external_key.this
}
```

[top](#index)