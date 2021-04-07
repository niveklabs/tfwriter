# sumologic_password_policy

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_password_policy" {
  source = "./modules/sumologic/r/sumologic_password_policy"

  # account_lockout_duration_in_mins - (optional) is a type of number
  account_lockout_duration_in_mins = null
  # account_lockout_threshold - (optional) is a type of number
  account_lockout_threshold = null
  # failed_login_reset_duration_in_mins - (optional) is a type of number
  failed_login_reset_duration_in_mins = null
  # max_length - (optional) is a type of number
  max_length = null
  # max_password_age_in_days - (optional) is a type of number
  max_password_age_in_days = null
  # min_length - (optional) is a type of number
  min_length = null
  # min_unique_passwords - (optional) is a type of number
  min_unique_passwords = null
  # must_contain_digits - (optional) is a type of bool
  must_contain_digits = null
  # must_contain_lowercase - (optional) is a type of bool
  must_contain_lowercase = null
  # must_contain_special_chars - (optional) is a type of bool
  must_contain_special_chars = null
  # must_contain_uppercase - (optional) is a type of bool
  must_contain_uppercase = null
  # remember_mfa - (optional) is a type of bool
  remember_mfa = null
  # require_mfa - (optional) is a type of bool
  require_mfa = null
}
```

[top](#index)

### Variables

```terraform
variable "account_lockout_duration_in_mins" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "account_lockout_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failed_login_reset_duration_in_mins" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_password_age_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_unique_passwords" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "must_contain_digits" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "must_contain_lowercase" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "must_contain_special_chars" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "must_contain_uppercase" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "remember_mfa" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "require_mfa" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_password_policy" "this" {
  # account_lockout_duration_in_mins - (optional) is a type of number
  account_lockout_duration_in_mins = var.account_lockout_duration_in_mins
  # account_lockout_threshold - (optional) is a type of number
  account_lockout_threshold = var.account_lockout_threshold
  # failed_login_reset_duration_in_mins - (optional) is a type of number
  failed_login_reset_duration_in_mins = var.failed_login_reset_duration_in_mins
  # max_length - (optional) is a type of number
  max_length = var.max_length
  # max_password_age_in_days - (optional) is a type of number
  max_password_age_in_days = var.max_password_age_in_days
  # min_length - (optional) is a type of number
  min_length = var.min_length
  # min_unique_passwords - (optional) is a type of number
  min_unique_passwords = var.min_unique_passwords
  # must_contain_digits - (optional) is a type of bool
  must_contain_digits = var.must_contain_digits
  # must_contain_lowercase - (optional) is a type of bool
  must_contain_lowercase = var.must_contain_lowercase
  # must_contain_special_chars - (optional) is a type of bool
  must_contain_special_chars = var.must_contain_special_chars
  # must_contain_uppercase - (optional) is a type of bool
  must_contain_uppercase = var.must_contain_uppercase
  # remember_mfa - (optional) is a type of bool
  remember_mfa = var.remember_mfa
  # require_mfa - (optional) is a type of bool
  require_mfa = var.require_mfa
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_password_policy.this.id
}

output "this" {
  value = sumologic_password_policy.this
}
```

[top](#index)