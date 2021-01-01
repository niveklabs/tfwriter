# aws_iam_user_policy

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
module "aws_iam_user_policy" {
  source = "./modules/aws/r/aws_iam_user_policy"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # policy - (required) is a type of string
  policy = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
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

```hcl
resource "aws_iam_user_policy" "this" {
  name        = var.name
  name_prefix = var.name_prefix
  policy      = var.policy
  user        = var.user
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_iam_user_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_user_policy.this.name
}

output "this" {
  value = aws_iam_user_policy.this
}
```

[top](#index)