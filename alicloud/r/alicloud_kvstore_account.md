# alicloud_kvstore_account

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
module "alicloud_kvstore_account" {
  source = "./modules/alicloud/r/alicloud_kvstore_account"

  # account_name - (required) is a type of string
  account_name = null
  # account_password - (optional) is a type of string
  account_password = null
  # account_privilege - (optional) is a type of string
  account_privilege = null
  # account_type - (optional) is a type of string
  account_type = null
  # description - (optional) is a type of string
  description = null
  # instance_id - (required) is a type of string
  instance_id = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "account_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_privilege" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_type" {
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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kvstore_account" "this" {
  account_name           = var.account_name
  account_password       = var.account_password
  account_privilege      = var.account_privilege
  account_type           = var.account_type
  description            = var.description
  instance_id            = var.instance_id
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_kvstore_account.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_kvstore_account.this.status
}

output "this" {
  value = alicloud_kvstore_account.this
}
```

[top](#index)