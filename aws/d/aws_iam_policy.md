# aws_iam_policy

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_policy" {
  source = "./modules/aws/d/aws_iam_policy"

  # arn - (required) is a type of string
  arn = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
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

```terraform
data "aws_iam_policy" "this" {
  # arn - (required) is a type of string
  arn = var.arn
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aws_iam_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_iam_policy.this.name
}

output "path" {
  description = "returns a string"
  value       = data.aws_iam_policy.this.path
}

output "policy" {
  description = "returns a string"
  value       = data.aws_iam_policy.this.policy
}

output "policy_id" {
  description = "returns a string"
  value       = data.aws_iam_policy.this.policy_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_iam_policy.this.tags
}

output "this" {
  value = aws_iam_policy.this
}
```

[top](#index)