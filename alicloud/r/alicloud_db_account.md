# alicloud_db_account

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
module "alicloud_db_account" {
  source = "./modules/alicloud/r/alicloud_db_account"

  # description - (optional) is a type of string
  description = null
  # instance_id - (required) is a type of string
  instance_id = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_account" "this" {
  description            = var.description
  instance_id            = var.instance_id
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context
  name                   = var.name
  password               = var.password
  type                   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_db_account.this.id
}

output "type" {
  description = "returns a string"
  value       = alicloud_db_account.this.type
}

output "this" {
  value = alicloud_db_account.this
}
```

[top](#index)