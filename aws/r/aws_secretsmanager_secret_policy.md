# aws_secretsmanager_secret_policy

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
module "aws_secretsmanager_secret_policy" {
  source = "./modules/aws/r/aws_secretsmanager_secret_policy"

  # block_public_policy - (optional) is a type of bool
  block_public_policy = null
  # policy - (required) is a type of string
  policy = null
  # secret_arn - (required) is a type of string
  secret_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "block_public_policy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policy" {
  description = "(required)"
  type        = string
}

variable "secret_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_secretsmanager_secret_policy" "this" {
  block_public_policy = var.block_public_policy
  policy              = var.policy
  secret_arn          = var.secret_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_secretsmanager_secret_policy.this.id
}

output "this" {
  value = aws_secretsmanager_secret_policy.this
}
```

[top](#index)