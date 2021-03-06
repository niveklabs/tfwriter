# aws_backup_vault

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_backup_vault" {
  source = "./modules/aws/d/aws_backup_vault"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_backup_vault" "this" {
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_backup_vault.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_backup_vault.this.id
}

output "kms_key_arn" {
  description = "returns a string"
  value       = data.aws_backup_vault.this.kms_key_arn
}

output "recovery_points" {
  description = "returns a number"
  value       = data.aws_backup_vault.this.recovery_points
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_backup_vault.this.tags
}

output "this" {
  value = aws_backup_vault.this
}
```

[top](#index)