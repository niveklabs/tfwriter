# aws_secretsmanager_secret_rotation

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
module "aws_secretsmanager_secret_rotation" {
  source = "./modules/aws/r/aws_secretsmanager_secret_rotation"

  # rotation_lambda_arn - (required) is a type of string
  rotation_lambda_arn = null
  # secret_id - (required) is a type of string
  secret_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  rotation_rules = [{
    automatically_after_days = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "rotation_lambda_arn" {
  description = "(required)"
  type        = string
}

variable "secret_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "rotation_rules" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      automatically_after_days = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_secretsmanager_secret_rotation" "this" {
  # rotation_lambda_arn - (required) is a type of string
  rotation_lambda_arn = var.rotation_lambda_arn
  # secret_id - (required) is a type of string
  secret_id = var.secret_id
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "rotation_rules" {
    for_each = var.rotation_rules
    content {
      # automatically_after_days - (required) is a type of number
      automatically_after_days = rotation_rules.value["automatically_after_days"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_secretsmanager_secret_rotation.this.id
}

output "rotation_enabled" {
  description = "returns a bool"
  value       = aws_secretsmanager_secret_rotation.this.rotation_enabled
}

output "this" {
  value = aws_secretsmanager_secret_rotation.this
}
```

[top](#index)