# aws_backup_vault_notifications

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
module "aws_backup_vault_notifications" {
  source = "./modules/aws/r/aws_backup_vault_notifications"

  # backup_vault_events - (required) is a type of set of string
  backup_vault_events = []
  # backup_vault_name - (required) is a type of string
  backup_vault_name = null
  # sns_topic_arn - (required) is a type of string
  sns_topic_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "backup_vault_events" {
  description = "(required)"
  type        = set(string)
}

variable "backup_vault_name" {
  description = "(required)"
  type        = string
}

variable "sns_topic_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_backup_vault_notifications" "this" {
  backup_vault_events = var.backup_vault_events
  backup_vault_name   = var.backup_vault_name
  sns_topic_arn       = var.sns_topic_arn
}
```

[top](#index)

### Outputs

```hcl
output "backup_vault_arn" {
  description = "returns a string"
  value       = aws_backup_vault_notifications.this.backup_vault_arn
}

output "id" {
  description = "returns a string"
  value       = aws_backup_vault_notifications.this.id
}

output "this" {
  value = aws_backup_vault_notifications.this
}
```

[top](#index)