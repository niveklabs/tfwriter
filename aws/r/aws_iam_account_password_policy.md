# aws_iam_account_password_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_account_password_policy" {
  source = "./modules/aws/r/aws_iam_account_password_policy"

  # allow_users_to_change_password - (optional) is a type of bool
  allow_users_to_change_password = null
  # hard_expiry - (optional) is a type of bool
  hard_expiry = null
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
variable "allow_users_to_change_password" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hard_expiry" {
  description = "(optional)"
  type        = bool
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
resource "aws_iam_account_password_policy" "this" {
  allow_users_to_change_password = var.allow_users_to_change_password
  hard_expiry                    = var.hard_expiry
  max_password_age               = var.max_password_age
  minimum_password_length        = var.minimum_password_length
  password_reuse_prevention      = var.password_reuse_prevention
  require_lowercase_characters   = var.require_lowercase_characters
  require_numbers                = var.require_numbers
  require_symbols                = var.require_symbols
  require_uppercase_characters   = var.require_uppercase_characters
}
```

[top](#index)

### Outputs

```terraform
output "expire_passwords" {
  description = "returns a bool"
  value       = aws_iam_account_password_policy.this.expire_passwords
}

output "hard_expiry" {
  description = "returns a bool"
  value       = aws_iam_account_password_policy.this.hard_expiry
}

output "id" {
  description = "returns a string"
  value       = aws_iam_account_password_policy.this.id
}

output "max_password_age" {
  description = "returns a number"
  value       = aws_iam_account_password_policy.this.max_password_age
}

output "password_reuse_prevention" {
  description = "returns a number"
  value       = aws_iam_account_password_policy.this.password_reuse_prevention
}

output "require_lowercase_characters" {
  description = "returns a bool"
  value       = aws_iam_account_password_policy.this.require_lowercase_characters
}

output "require_numbers" {
  description = "returns a bool"
  value       = aws_iam_account_password_policy.this.require_numbers
}

output "require_symbols" {
  description = "returns a bool"
  value       = aws_iam_account_password_policy.this.require_symbols
}

output "require_uppercase_characters" {
  description = "returns a bool"
  value       = aws_iam_account_password_policy.this.require_uppercase_characters
}

output "this" {
  value = aws_iam_account_password_policy.this
}
```

[top](#index)