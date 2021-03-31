# aws_iam_policy

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_policy" {
  source = "./modules/aws/r/aws_iam_policy"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path - (optional) is a type of string
  path = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "path" {
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
resource "aws_iam_policy" "this" {
  description = var.description
  name        = var.name
  name_prefix = var.name_prefix
  path        = var.path
  policy      = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_policy.this.name
}

output "this" {
  value = aws_iam_policy.this
}
```

[top](#index)