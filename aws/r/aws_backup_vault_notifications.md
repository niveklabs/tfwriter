# aws_backup_vault_notifications

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

```terraform
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

```terraform
resource "aws_backup_vault_notifications" "this" {
  # backup_vault_events - (required) is a type of set of string
  backup_vault_events = var.backup_vault_events
  # backup_vault_name - (required) is a type of string
  backup_vault_name = var.backup_vault_name
  # sns_topic_arn - (required) is a type of string
  sns_topic_arn = var.sns_topic_arn
}
```

[top](#index)

### Outputs

```terraform
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