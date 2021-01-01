# aws_opsworks_permission

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_opsworks_permission" {
  source = "./modules/aws/r/aws_opsworks_permission"

  # allow_ssh - (optional) is a type of bool
  allow_ssh = null
  # allow_sudo - (optional) is a type of bool
  allow_sudo = null
  # level - (optional) is a type of string
  level = null
  # stack_id - (optional) is a type of string
  stack_id = null
  # user_arn - (required) is a type of string
  user_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "allow_ssh" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_sudo" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_opsworks_permission" "this" {
  allow_ssh  = var.allow_ssh
  allow_sudo = var.allow_sudo
  level      = var.level
  stack_id   = var.stack_id
  user_arn   = var.user_arn
}
```

[top](#index)

### Outputs

```hcl
output "allow_ssh" {
  description = "returns a bool"
  value       = aws_opsworks_permission.this.allow_ssh
}

output "allow_sudo" {
  description = "returns a bool"
  value       = aws_opsworks_permission.this.allow_sudo
}

output "id" {
  description = "returns a string"
  value       = aws_opsworks_permission.this.id
}

output "level" {
  description = "returns a string"
  value       = aws_opsworks_permission.this.level
}

output "stack_id" {
  description = "returns a string"
  value       = aws_opsworks_permission.this.stack_id
}

output "this" {
  value = aws_opsworks_permission.this
}
```

[top](#index)