# aws_iam_group_policy_attachment

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
module "aws_iam_group_policy_attachment" {
  source = "./modules/aws/r/aws_iam_group_policy_attachment"

  # group - (required) is a type of string
  group = null
  # policy_arn - (required) is a type of string
  policy_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "group" {
  description = "(required)"
  type        = string
}

variable "policy_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_iam_group_policy_attachment" "this" {
  group      = var.group
  policy_arn = var.policy_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_iam_group_policy_attachment.this.id
}

output "this" {
  value = aws_iam_group_policy_attachment.this
}
```

[top](#index)