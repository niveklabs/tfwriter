# aws_iam_policy

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
module "aws_iam_policy" {
  source = "./modules/aws/d/aws_iam_policy"

  # arn - (required) is a type of string
  arn = null
}
```

[top](#index)

### Variables

```hcl
variable "arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_iam_policy" "this" {
  arn = var.arn
}
```

[top](#index)

### Outputs

```hcl
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

output "this" {
  value = aws_iam_policy.this
}
```

[top](#index)