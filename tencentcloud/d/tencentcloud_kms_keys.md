# tencentcloud_kms_keys

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_kms_keys" {
  source = "./modules/tencentcloud/d/tencentcloud_kms_keys"

  # key_state - (optional) is a type of number
  key_state = null
  # key_usage - (optional) is a type of string
  key_usage = null
  # order_type - (optional) is a type of number
  order_type = null
  # origin - (optional) is a type of string
  origin = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # role - (optional) is a type of number
  role = null
  # search_key_alias - (optional) is a type of string
  search_key_alias = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "key_state" {
  description = "(optional) - Filter by state of CMK. `0` - all CMKs are queried, `1` - only Enabled CMKs are queried, `2` - only Disabled CMKs are queried, `3` - only PendingDelete CMKs are queried, `4` - only PendingImport CMKs are queried, `5` - only Archived CMKs are queried."
  type        = number
  default     = null
}

variable "key_usage" {
  description = "(optional) - Filter by usage of CMK. Available values include `ALL`, `ENCRYPT_DECRYPT`, `ASYMMETRIC_DECRYPT_RSA_2048`, `ASYMMETRIC_DECRYPT_SM2`, `ASYMMETRIC_SIGN_VERIFY_SM2`, `ASYMMETRIC_SIGN_VERIFY_RSA_2048`, `ASYMMETRIC_SIGN_VERIFY_ECC`. Default value is `ENCRYPT_DECRYPT`."
  type        = string
  default     = null
}

variable "order_type" {
  description = "(optional) - Order to sort the CMK create time. `0` - desc, `1` - asc. Default value is `0`."
  type        = number
  default     = null
}

variable "origin" {
  description = "(optional) - Filter by origin of CMK. `TENCENT_KMS` - CMK created by KMS, `EXTERNAL` - CMK imported by user, `ALL` - all CMKs. Default value is `ALL`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "role" {
  description = "(optional) - Filter by role of the CMK creator. `0` - created by user, `1` - created by cloud product. Default value is `0`."
  type        = number
  default     = null
}

variable "search_key_alias" {
  description = "(optional) - Words used to match the results, and the words can be: key_id and alias."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags to filter CMK."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_kms_keys" "this" {
  # key_state - (optional) is a type of number
  key_state = var.key_state
  # key_usage - (optional) is a type of string
  key_usage = var.key_usage
  # order_type - (optional) is a type of number
  order_type = var.order_type
  # origin - (optional) is a type of string
  origin = var.origin
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # role - (optional) is a type of number
  role = var.role
  # search_key_alias - (optional) is a type of string
  search_key_alias = var.search_key_alias
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_kms_keys.this.id
}

output "key_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_kms_keys.this.key_list
}

output "this" {
  value = tencentcloud_kms_keys.this
}
```

[top](#index)