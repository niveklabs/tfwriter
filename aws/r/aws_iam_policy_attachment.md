# aws_iam_policy_attachment

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
module "aws_iam_policy_attachment" {
  source = "./modules/aws/r/aws_iam_policy_attachment"

  # groups - (optional) is a type of set of string
  groups = []
  # name - (required) is a type of string
  name = null
  # policy_arn - (required) is a type of string
  policy_arn = null
  # roles - (optional) is a type of set of string
  roles = []
  # users - (optional) is a type of set of string
  users = []
}
```

[top](#index)

### Variables

```terraform
variable "groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_arn" {
  description = "(required)"
  type        = string
}

variable "roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "users" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_policy_attachment" "this" {
  groups     = var.groups
  name       = var.name
  policy_arn = var.policy_arn
  roles      = var.roles
  users      = var.users
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_policy_attachment.this.id
}

output "this" {
  value = aws_iam_policy_attachment.this
}
```

[top](#index)