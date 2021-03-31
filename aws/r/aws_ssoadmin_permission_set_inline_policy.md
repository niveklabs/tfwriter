# aws_ssoadmin_permission_set_inline_policy

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
module "aws_ssoadmin_permission_set_inline_policy" {
  source = "./modules/aws/r/aws_ssoadmin_permission_set_inline_policy"

  # inline_policy - (required) is a type of string
  inline_policy = null
  # instance_arn - (required) is a type of string
  instance_arn = null
  # permission_set_arn - (required) is a type of string
  permission_set_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "inline_policy" {
  description = "(required)"
  type        = string
}

variable "instance_arn" {
  description = "(required)"
  type        = string
}

variable "permission_set_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssoadmin_permission_set_inline_policy" "this" {
  inline_policy      = var.inline_policy
  instance_arn       = var.instance_arn
  permission_set_arn = var.permission_set_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssoadmin_permission_set_inline_policy.this.id
}

output "this" {
  value = aws_ssoadmin_permission_set_inline_policy.this
}
```

[top](#index)