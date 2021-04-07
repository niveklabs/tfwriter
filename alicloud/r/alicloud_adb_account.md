# alicloud_adb_account

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
module "alicloud_adb_account" {
  source = "./modules/alicloud/r/alicloud_adb_account"

  # account_description - (optional) is a type of string
  account_description = null
  # account_name - (required) is a type of string
  account_name = null
  # account_password - (optional) is a type of string
  account_password = null
  # account_type - (optional) is a type of string
  account_type = null
  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
}
```

[top](#index)

### Variables

```terraform
variable "account_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_name" {
  description = "(required)"
  type        = string
}

variable "account_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "kms_encrypted_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encryption_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_adb_account" "this" {
  # account_description - (optional) is a type of string
  account_description = var.account_description
  # account_name - (required) is a type of string
  account_name = var.account_name
  # account_password - (optional) is a type of string
  account_password = var.account_password
  # account_type - (optional) is a type of string
  account_type = var.account_type
  # db_cluster_id - (required) is a type of string
  db_cluster_id = var.db_cluster_id
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = var.kms_encrypted_password
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = var.kms_encryption_context
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_adb_account.this.id
}

output "this" {
  value = alicloud_adb_account.this
}
```

[top](#index)