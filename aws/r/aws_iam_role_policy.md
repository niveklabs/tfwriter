# aws_iam_role_policy

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
module "aws_iam_role_policy" {
  source = "./modules/aws/r/aws_iam_role_policy"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # policy - (required) is a type of string
  policy = null
  # role - (required) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
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

variable "policy" {
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
resource "aws_iam_role_policy" "this" {
  name        = var.name
  name_prefix = var.name_prefix
  policy      = var.policy
  role        = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_role_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_role_policy.this.name
}

output "this" {
  value = aws_iam_role_policy.this
}
```

[top](#index)