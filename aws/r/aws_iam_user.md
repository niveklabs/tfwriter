# aws_iam_user

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
module "aws_iam_user" {
  source = "./modules/aws/r/aws_iam_user"

  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # permissions_boundary - (optional) is a type of string
  permissions_boundary = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "force_destroy" {
  description = "(optional) - Delete user even if it has non-Terraform-managed IAM access keys, login profile or MFA devices"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permissions_boundary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_user" "this" {
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # name - (required) is a type of string
  name = var.name
  # path - (optional) is a type of string
  path = var.path
  # permissions_boundary - (optional) is a type of string
  permissions_boundary = var.permissions_boundary
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_user.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_user.this.id
}

output "unique_id" {
  description = "returns a string"
  value       = aws_iam_user.this.unique_id
}

output "this" {
  value = aws_iam_user.this
}
```

[top](#index)