# alicloud_alikafka_sasl_user

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_alikafka_sasl_user" {
  source = "./modules/alicloud/r/alicloud_alikafka_sasl_user"

  # instance_id - (required) is a type of string
  instance_id = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # password - (optional) is a type of string
  password = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
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

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alikafka_sasl_user" "this" {
  instance_id            = var.instance_id
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context
  password               = var.password
  username               = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_alikafka_sasl_user.this.id
}

output "this" {
  value = alicloud_alikafka_sasl_user.this
}
```

[top](#index)