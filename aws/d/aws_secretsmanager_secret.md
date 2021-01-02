# aws_secretsmanager_secret

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_secretsmanager_secret" {
  source = "./modules/aws/d/aws_secretsmanager_secret"

  # arn - (optional) is a type of string
  arn = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_secretsmanager_secret" "this" {
  arn  = var.arn
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.kms_key_id
}

output "name" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.name
}

output "policy" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.policy
}

output "rotation_enabled" {
  description = "returns a bool"
  value       = data.aws_secretsmanager_secret.this.rotation_enabled
}

output "rotation_lambda_arn" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret.this.rotation_lambda_arn
}

output "rotation_rules" {
  description = "returns a list of object"
  value       = data.aws_secretsmanager_secret.this.rotation_rules
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_secretsmanager_secret.this.tags
}

output "this" {
  value = aws_secretsmanager_secret.this
}
```

[top](#index)