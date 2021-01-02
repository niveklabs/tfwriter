# aws_iam_user_login_profile

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_user_login_profile" {
  source = "./modules/aws/r/aws_iam_user_login_profile"

  # password_length - (optional) is a type of number
  password_length = null
  # password_reset_required - (optional) is a type of bool
  password_reset_required = null
  # pgp_key - (required) is a type of string
  pgp_key = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "password_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password_reset_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "pgp_key" {
  description = "(required)"
  type        = string
}

variable "user" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_user_login_profile" "this" {
  password_length         = var.password_length
  password_reset_required = var.password_reset_required
  pgp_key                 = var.pgp_key
  user                    = var.user
}
```

[top](#index)

### Outputs

```terraform
output "encrypted_password" {
  description = "returns a string"
  value       = aws_iam_user_login_profile.this.encrypted_password
}

output "id" {
  description = "returns a string"
  value       = aws_iam_user_login_profile.this.id
}

output "key_fingerprint" {
  description = "returns a string"
  value       = aws_iam_user_login_profile.this.key_fingerprint
}

output "this" {
  value = aws_iam_user_login_profile.this
}
```

[top](#index)