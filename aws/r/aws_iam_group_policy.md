# aws_iam_group_policy

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
module "aws_iam_group_policy" {
  source = "./modules/aws/r/aws_iam_group_policy"

  # group - (required) is a type of string
  group = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "group" {
  description = "(required)"
  type        = string
}

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
```

[top](#index)

### Resource

```terraform
resource "aws_iam_group_policy" "this" {
  # group - (required) is a type of string
  group = var.group
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # policy - (required) is a type of string
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_group_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_group_policy.this.name
}

output "this" {
  value = aws_iam_group_policy.this
}
```

[top](#index)