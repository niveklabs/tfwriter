# alicloud_sag_client_user

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
module "alicloud_sag_client_user" {
  source = "./modules/alicloud/r/alicloud_sag_client_user"

  # bandwidth - (required) is a type of number
  bandwidth = null
  # client_ip - (optional) is a type of string
  client_ip = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # password - (optional) is a type of string
  password = null
  # sag_id - (required) is a type of string
  sag_id = null
  # user_mail - (required) is a type of string
  user_mail = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = number
}

variable "client_ip" {
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

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sag_id" {
  description = "(required)"
  type        = string
}

variable "user_mail" {
  description = "(required)"
  type        = string
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_sag_client_user" "this" {
  bandwidth              = var.bandwidth
  client_ip              = var.client_ip
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context
  password               = var.password
  sag_id                 = var.sag_id
  user_mail              = var.user_mail
  user_name              = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_sag_client_user.this.id
}

output "password" {
  description = "returns a string"
  value       = alicloud_sag_client_user.this.password
}

output "user_name" {
  description = "returns a string"
  value       = alicloud_sag_client_user.this.user_name
}

output "this" {
  value = alicloud_sag_client_user.this
}
```

[top](#index)