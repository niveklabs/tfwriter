# aws_secretsmanager_secret_rotation

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

```hcl
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
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      automatically_after_days = number
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_secretsmanager_secret_rotation" "this" {
  rotation_lambda_arn = var.rotation_lambda_arn
  secret_id           = var.secret_id
  tags                = var.tags

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

```hcl
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