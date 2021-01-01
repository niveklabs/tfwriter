# aws_iam_role

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_iam_role" {
  source = "./modules/aws/d/aws_iam_role"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_iam_role" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_iam_role.this.arn
}

output "assume_role_policy" {
  description = "returns a string"
  value       = data.aws_iam_role.this.assume_role_policy
}

output "create_date" {
  description = "returns a string"
  value       = data.aws_iam_role.this.create_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_iam_role.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_role.this.id
}

output "max_session_duration" {
  description = "returns a number"
  value       = data.aws_iam_role.this.max_session_duration
}

output "path" {
  description = "returns a string"
  value       = data.aws_iam_role.this.path
}

output "permissions_boundary" {
  description = "returns a string"
  value       = data.aws_iam_role.this.permissions_boundary
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_iam_role.this.tags
}

output "unique_id" {
  description = "returns a string"
  value       = data.aws_iam_role.this.unique_id
}

output "this" {
  value = aws_iam_role.this
}
```

[top](#index)