# aws_opsworks_user_profile

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
module "aws_opsworks_user_profile" {
  source = "./modules/aws/r/aws_opsworks_user_profile"

  # allow_self_management - (optional) is a type of bool
  allow_self_management = null
  # ssh_public_key - (optional) is a type of string
  ssh_public_key = null
  # ssh_username - (required) is a type of string
  ssh_username = null
  # user_arn - (required) is a type of string
  user_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_self_management" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssh_public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_username" {
  description = "(required)"
  type        = string
}

variable "user_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_opsworks_user_profile" "this" {
  # allow_self_management - (optional) is a type of bool
  allow_self_management = var.allow_self_management
  # ssh_public_key - (optional) is a type of string
  ssh_public_key = var.ssh_public_key
  # ssh_username - (required) is a type of string
  ssh_username = var.ssh_username
  # user_arn - (required) is a type of string
  user_arn = var.user_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_opsworks_user_profile.this.id
}

output "this" {
  value = aws_opsworks_user_profile.this
}
```

[top](#index)