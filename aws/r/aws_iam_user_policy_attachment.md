# aws_iam_user_policy_attachment

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_user_policy_attachment" {
  source = "./modules/aws/r/aws_iam_user_policy_attachment"

  # policy_arn - (required) is a type of string
  policy_arn = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_arn" {
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

```terraform
resource "aws_iam_user_policy_attachment" "this" {
  policy_arn = var.policy_arn
  user       = var.user
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_user_policy_attachment.this.id
}

output "this" {
  value = aws_iam_user_policy_attachment.this
}
```

[top](#index)