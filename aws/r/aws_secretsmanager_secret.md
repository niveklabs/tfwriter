# aws_secretsmanager_secret

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
module "aws_secretsmanager_secret" {
  source = "./modules/aws/r/aws_secretsmanager_secret"

  # description - (optional) is a type of string
  description = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # policy - (optional) is a type of string
  policy = null
  # recovery_window_in_days - (optional) is a type of number
  recovery_window_in_days = null
  # rotation_lambda_arn - (optional) is a type of string
  rotation_lambda_arn = null
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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "recovery_window_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rotation_lambda_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "rotation_rules" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      automatically_after_days = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_secretsmanager_secret" "this" {
  description             = var.description
  kms_key_id              = var.kms_key_id
  name                    = var.name
  name_prefix             = var.name_prefix
  policy                  = var.policy
  recovery_window_in_days = var.recovery_window_in_days
  rotation_lambda_arn     = var.rotation_lambda_arn
  tags                    = var.tags

  dynamic "rotation_rules" {
    for_each = var.rotation_rules
    content {
      automatically_after_days = rotation_rules.value["automatically_after_days"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_secretsmanager_secret.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_secretsmanager_secret.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_secretsmanager_secret.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_secretsmanager_secret.this.name_prefix
}

output "policy" {
  description = "returns a string"
  value       = aws_secretsmanager_secret.this.policy
}

output "rotation_enabled" {
  description = "returns a bool"
  value       = aws_secretsmanager_secret.this.rotation_enabled
}

output "rotation_lambda_arn" {
  description = "returns a string"
  value       = aws_secretsmanager_secret.this.rotation_lambda_arn
}

output "this" {
  value = aws_secretsmanager_secret.this
}
```

[top](#index)