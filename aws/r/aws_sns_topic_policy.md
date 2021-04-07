# aws_sns_topic_policy

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
module "aws_sns_topic_policy" {
  source = "./modules/aws/r/aws_sns_topic_policy"

  # arn - (required) is a type of string
  arn = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_sns_topic_policy" "this" {
  # arn - (required) is a type of string
  arn = var.arn
  # policy - (required) is a type of string
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_sns_topic_policy.this.id
}

output "this" {
  value = aws_sns_topic_policy.this
}
```

[top](#index)