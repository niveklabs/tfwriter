# aws_iam_user

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_user" {
  source = "./modules/aws/d/aws_iam_user"

  # tags - (optional) is a type of map of string
  tags = {}
  # user_name - (required) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_iam_user" "this" {
  tags      = var.tags
  user_name = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_iam_user.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_user.this.id
}

output "path" {
  description = "returns a string"
  value       = data.aws_iam_user.this.path
}

output "permissions_boundary" {
  description = "returns a string"
  value       = data.aws_iam_user.this.permissions_boundary
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_iam_user.this.tags
}

output "user_id" {
  description = "returns a string"
  value       = data.aws_iam_user.this.user_id
}

output "this" {
  value = aws_iam_user.this
}
```

[top](#index)