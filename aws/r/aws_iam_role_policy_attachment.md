# aws_iam_role_policy_attachment

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
module "aws_iam_role_policy_attachment" {
  source = "./modules/aws/r/aws_iam_role_policy_attachment"

  # policy_arn - (required) is a type of string
  policy_arn = null
  # role - (required) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_arn" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_role_policy_attachment" "this" {
  # policy_arn - (required) is a type of string
  policy_arn = var.policy_arn
  # role - (required) is a type of string
  role = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_role_policy_attachment.this.id
}

output "this" {
  value = aws_iam_role_policy_attachment.this
}
```

[top](#index)