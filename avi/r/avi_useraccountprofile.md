# avi_useraccountprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_useraccountprofile" {
  source = "./modules/avi/r/avi_useraccountprofile"

  # account_lock_timeout - (optional) is a type of number
  account_lock_timeout = null
  # credentials_timeout_threshold - (optional) is a type of number
  credentials_timeout_threshold = null
  # max_concurrent_sessions - (optional) is a type of number
  max_concurrent_sessions = null
  # max_login_failure_count - (optional) is a type of number
  max_login_failure_count = null
  # max_password_history_count - (optional) is a type of number
  max_password_history_count = null
  # name - (required) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "account_lock_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "credentials_timeout_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_concurrent_sessions" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_login_failure_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_password_history_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_useraccountprofile" "this" {
  # account_lock_timeout - (optional) is a type of number
  account_lock_timeout = var.account_lock_timeout
  # credentials_timeout_threshold - (optional) is a type of number
  credentials_timeout_threshold = var.credentials_timeout_threshold
  # max_concurrent_sessions - (optional) is a type of number
  max_concurrent_sessions = var.max_concurrent_sessions
  # max_login_failure_count - (optional) is a type of number
  max_login_failure_count = var.max_login_failure_count
  # max_password_history_count - (optional) is a type of number
  max_password_history_count = var.max_password_history_count
  # name - (required) is a type of string
  name = var.name
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_useraccountprofile.this.id
}

output "uuid" {
  description = "returns a string"
  value       = avi_useraccountprofile.this.uuid
}

output "this" {
  value = avi_useraccountprofile.this
}
```

[top](#index)