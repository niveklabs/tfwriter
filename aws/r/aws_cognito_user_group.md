# aws_cognito_user_group

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
module "aws_cognito_user_group" {
  source = "./modules/aws/r/aws_cognito_user_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # precedence - (optional) is a type of number
  precedence = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # user_pool_id - (required) is a type of string
  user_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "precedence" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_pool_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cognito_user_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # precedence - (optional) is a type of number
  precedence = var.precedence
  # role_arn - (optional) is a type of string
  role_arn = var.role_arn
  # user_pool_id - (required) is a type of string
  user_pool_id = var.user_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cognito_user_group.this.id
}

output "this" {
  value = aws_cognito_user_group.this
}
```

[top](#index)