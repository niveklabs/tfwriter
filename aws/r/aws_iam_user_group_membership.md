# aws_iam_user_group_membership

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
module "aws_iam_user_group_membership" {
  source = "./modules/aws/r/aws_iam_user_group_membership"

  # groups - (required) is a type of set of string
  groups = []
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "groups" {
  description = "(required)"
  type        = set(string)
}

variable "user" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_user_group_membership" "this" {
  # groups - (required) is a type of set of string
  groups = var.groups
  # user - (required) is a type of string
  user = var.user
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_user_group_membership.this.id
}

output "this" {
  value = aws_iam_user_group_membership.this
}
```

[top](#index)