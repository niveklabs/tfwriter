# aws_ecr_lifecycle_policy

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
module "aws_ecr_lifecycle_policy" {
  source = "./modules/aws/r/aws_ecr_lifecycle_policy"

  # policy - (required) is a type of string
  policy = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "policy" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ecr_lifecycle_policy" "this" {
  # policy - (required) is a type of string
  policy = var.policy
  # repository - (required) is a type of string
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ecr_lifecycle_policy.this.id
}

output "registry_id" {
  description = "returns a string"
  value       = aws_ecr_lifecycle_policy.this.registry_id
}

output "this" {
  value = aws_ecr_lifecycle_policy.this
}
```

[top](#index)