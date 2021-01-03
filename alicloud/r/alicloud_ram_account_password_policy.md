# alicloud_ram_account_password_policy

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
module "alicloud_ram_account_password_policy" {
  source = "./modules/alicloud/r/alicloud_ram_account_password_policy"

  # hard_expiry - (optional) is a type of bool
  hard_expiry = null
  # max_login_attempts - (optional) is a type of number
  max_login_attempts = null
  # max_password_age - (optional) is a type of number
  max_password_age = null
  # minimum_password_length - (optional) is a type of number
  minimum_password_length = null
  # password_reuse_prevention - (optional) is a type of number
  password_reuse_prevention = null
  # require_lowercase_characters - (optional) is a type of bool
  require_lowercase_characters = null
  # require_numbers - (optional) is a type of bool
  require_numbers = null
  # require_symbols - (optional) is a type of bool
  require_symbols = null
  # require_uppercase_characters - (optional) is a type of bool
  require_uppercase_characters = null
}
```

[top](#index)

### Variables

```terraform
variable "hard_expiry" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_login_attempts" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_password_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minimum_password_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password_reuse_prevention" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "require_lowercase_characters" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "require_numbers" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "require_symbols" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "require_uppercase_characters" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_account_password_policy" "this" {
  hard_expiry                  = var.hard_expiry
  max_login_attempts           = var.max_login_attempts
  max_password_age             = var.max_password_age
  minimum_password_length      = var.minimum_password_length
  password_reuse_prevention    = var.password_reuse_prevention
  require_lowercase_characters = var.require_lowercase_characters
  require_numbers              = var.require_numbers
  require_symbols              = var.require_symbols
  require_uppercase_characters = var.require_uppercase_characters
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_account_password_policy.this.id
}

output "this" {
  value = alicloud_ram_account_password_policy.this
}
```

[top](#index)