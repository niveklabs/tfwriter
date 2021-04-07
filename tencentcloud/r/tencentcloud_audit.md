# tencentcloud_audit

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
module "tencentcloud_audit" {
  source = "./modules/tencentcloud/r/tencentcloud_audit"

  # audit_switch - (required) is a type of bool
  audit_switch = null
  # cos_bucket - (required) is a type of string
  cos_bucket = null
  # cos_region - (required) is a type of string
  cos_region = null
  # enable_kms_encry - (optional) is a type of bool
  enable_kms_encry = null
  # key_id - (optional) is a type of string
  key_id = null
  # log_file_prefix - (optional) is a type of string
  log_file_prefix = null
  # name - (required) is a type of string
  name = null
  # read_write_attribute - (required) is a type of number
  read_write_attribute = null
}
```

[top](#index)

### Variables

```terraform
variable "audit_switch" {
  description = "(required) - Indicate whether to turn on audit logging or not."
  type        = bool
}

variable "cos_bucket" {
  description = "(required) - Name of the cos bucket to save audit log. Caution: the validation of existing cos bucket will not be checked by terraform."
  type        = string
}

variable "cos_region" {
  description = "(required) - Region of the cos bucket."
  type        = string
}

variable "enable_kms_encry" {
  description = "(optional) - Indicate whether the log is encrypt with KMS algorithm or not."
  type        = bool
  default     = null
}

variable "key_id" {
  description = "(optional) - Existing CMK unique key. This field can be get by data source `tencentcloud_audit_key_alias`. Caution: the region of the KMS must be as same as the `cos_region`."
  type        = string
  default     = null
}

variable "log_file_prefix" {
  description = "(optional) - The log file name prefix. The length ranges from 3 to 40. If not set, the account ID will be the log file prefix."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of audit. Valid length ranges from 3 to 128. Only alpha character or numbers or '_' supported."
  type        = string
}

variable "read_write_attribute" {
  description = "(required) - Event attribute filter. Valid values: `1`, `2`, `3`. `1` for readonly, `2` for write-only, `3` for all."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_audit" "this" {
  # audit_switch - (required) is a type of bool
  audit_switch = var.audit_switch
  # cos_bucket - (required) is a type of string
  cos_bucket = var.cos_bucket
  # cos_region - (required) is a type of string
  cos_region = var.cos_region
  # enable_kms_encry - (optional) is a type of bool
  enable_kms_encry = var.enable_kms_encry
  # key_id - (optional) is a type of string
  key_id = var.key_id
  # log_file_prefix - (optional) is a type of string
  log_file_prefix = var.log_file_prefix
  # name - (required) is a type of string
  name = var.name
  # read_write_attribute - (required) is a type of number
  read_write_attribute = var.read_write_attribute
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_audit.this.id
}

output "log_file_prefix" {
  description = "returns a string"
  value       = tencentcloud_audit.this.log_file_prefix
}

output "this" {
  value = tencentcloud_audit.this
}
```

[top](#index)