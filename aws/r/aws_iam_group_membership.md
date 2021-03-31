# aws_iam_group_membership

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
module "aws_iam_group_membership" {
  source = "./modules/aws/r/aws_iam_group_membership"

  # group - (required) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
  # users - (required) is a type of set of string
  users = []
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
  description = "(required)"
  type        = string
}

variable "users" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_group_membership" "this" {
  group = var.group
  name  = var.name
  users = var.users
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_group_membership.this.id
}

output "this" {
  value = aws_iam_group_membership.this
}
```

[top](#index)