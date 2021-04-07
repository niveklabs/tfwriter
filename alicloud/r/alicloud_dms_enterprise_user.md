# alicloud_dms_enterprise_user

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
module "alicloud_dms_enterprise_user" {
  source = "./modules/alicloud/r/alicloud_dms_enterprise_user"

  # max_execute_count - (optional) is a type of number
  max_execute_count = null
  # max_result_count - (optional) is a type of number
  max_result_count = null
  # mobile - (optional) is a type of string
  mobile = null
  # nick_name - (optional) is a type of string
  nick_name = null
  # role_names - (optional) is a type of set of string
  role_names = []
  # status - (optional) is a type of string
  status = null
  # tid - (optional) is a type of number
  tid = null
  # uid - (required) is a type of string
  uid = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "max_execute_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_result_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mobile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nick_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uid" {
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
resource "alicloud_dms_enterprise_user" "this" {
  # max_execute_count - (optional) is a type of number
  max_execute_count = var.max_execute_count
  # max_result_count - (optional) is a type of number
  max_result_count = var.max_result_count
  # mobile - (optional) is a type of string
  mobile = var.mobile
  # nick_name - (optional) is a type of string
  nick_name = var.nick_name
  # role_names - (optional) is a type of set of string
  role_names = var.role_names
  # status - (optional) is a type of string
  status = var.status
  # tid - (optional) is a type of number
  tid = var.tid
  # uid - (required) is a type of string
  uid = var.uid
  # user_name - (optional) is a type of string
  user_name = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_user.this.id
}

output "nick_name" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_user.this.nick_name
}

output "user_name" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_user.this.user_name
}

output "this" {
  value = alicloud_dms_enterprise_user.this
}
```

[top](#index)