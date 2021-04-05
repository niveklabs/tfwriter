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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_db_account" {
  source = "./modules/alicloud/r/alicloud_db_account"

  # account_description - (optional) is a type of string
  account_description = null
  # account_name - (optional) is a type of string
  account_name = null
  # account_password - (optional) is a type of string
  account_password = null
  # account_type - (optional) is a type of string
  account_type = null
  # db_instance_id - (optional) is a type of string
  db_instance_id = null
  # description - (optional) is a type of string
  description = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
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
  description = "(optional)"
  type        = string
  default     = null
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

variable "db_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
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
  description = "(optional)"
  type        = string
  default     = null
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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_account" "this" {
  account_description    = var.account_description
  account_name           = var.account_name
  account_password       = var.account_password
  account_type           = var.account_type
  db_instance_id         = var.db_instance_id
  description            = var.description
  instance_id            = var.instance_id
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context
  name                   = var.name
  password               = var.password
  type                   = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_description" {
  description = "returns a string"
  value       = alicloud_db_account.this.account_description
}

output "account_name" {
  description = "returns a string"
  value       = alicloud_db_account.this.account_name
}

output "account_password" {
  description = "returns a string"
  value       = alicloud_db_account.this.account_password
  sensitive   = true
}

output "account_type" {
  description = "returns a string"
  value       = alicloud_db_account.this.account_type
}

output "db_instance_id" {
  description = "returns a string"
  value       = alicloud_db_account.this.db_instance_id
}

output "description" {
  description = "returns a string"
  value       = alicloud_db_account.this.description
}

output "id" {
  description = "returns a string"
  value       = alicloud_db_account.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = alicloud_db_account.this.instance_id
}

output "name" {
  description = "returns a string"
  value       = alicloud_db_account.this.name
}

output "password" {
  description = "returns a string"
  value       = alicloud_db_account.this.password
  sensitive   = true
}

output "status" {
  description = "returns a string"
  value       = alicloud_db_account.this.status
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