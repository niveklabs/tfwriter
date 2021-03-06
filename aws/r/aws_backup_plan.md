# aws_backup_plan

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
module "aws_backup_plan" {
  source = "./modules/aws/r/aws_backup_plan"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  advanced_backup_setting = [{
    backup_options = {}
    resource_type  = null
  }]

  rule = [{
    completion_window = null
    copy_action = [{
      destination_vault_arn = null
      lifecycle = [{
        cold_storage_after = null
        delete_after       = null
      }]
    }]
    enable_continuous_backup = null
    lifecycle = [{
      cold_storage_after = null
      delete_after       = null
    }]
    recovery_point_tags = {}
    rule_name           = null
    schedule            = null
    start_window        = null
    target_vault_name   = null
  }]
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

variable "advanced_backup_setting" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      backup_options = map(string)
      resource_type  = string
    }
  ))
  default = []
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      completion_window = number
      copy_action = set(object(
        {
          destination_vault_arn = string
          lifecycle = list(object(
            {
              cold_storage_after = number
              delete_after       = number
            }
          ))
        }
      ))
      enable_continuous_backup = bool
      lifecycle = list(object(
        {
          cold_storage_after = number
          delete_after       = number
        }
      ))
      recovery_point_tags = map(string)
      rule_name           = string
      schedule            = string
      start_window        = number
      target_vault_name   = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_backup_plan" "this" {
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "advanced_backup_setting" {
    for_each = var.advanced_backup_setting
    content {
      # backup_options - (required) is a type of map of string
      backup_options = advanced_backup_setting.value["backup_options"]
      # resource_type - (required) is a type of string
      resource_type = advanced_backup_setting.value["resource_type"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {
      # completion_window - (optional) is a type of number
      completion_window = rule.value["completion_window"]
      # enable_continuous_backup - (optional) is a type of bool
      enable_continuous_backup = rule.value["enable_continuous_backup"]
      # recovery_point_tags - (optional) is a type of map of string
      recovery_point_tags = rule.value["recovery_point_tags"]
      # rule_name - (required) is a type of string
      rule_name = rule.value["rule_name"]
      # schedule - (optional) is a type of string
      schedule = rule.value["schedule"]
      # start_window - (optional) is a type of number
      start_window = rule.value["start_window"]
      # target_vault_name - (required) is a type of string
      target_vault_name = rule.value["target_vault_name"]

      dynamic "copy_action" {
        for_each = rule.value.copy_action
        content {
          # destination_vault_arn - (required) is a type of string
          destination_vault_arn = copy_action.value["destination_vault_arn"]

          dynamic "lifecycle" {
            for_each = copy_action.value.lifecycle
            content {
              # cold_storage_after - (optional) is a type of number
              cold_storage_after = lifecycle.value["cold_storage_after"]
              # delete_after - (optional) is a type of number
              delete_after = lifecycle.value["delete_after"]
            }
          }

        }
      }

      dynamic "lifecycle" {
        for_each = rule.value.lifecycle
        content {
          # cold_storage_after - (optional) is a type of number
          cold_storage_after = lifecycle.value["cold_storage_after"]
          # delete_after - (optional) is a type of number
          delete_after = lifecycle.value["delete_after"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_backup_plan.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_backup_plan.this.id
}

output "version" {
  description = "returns a string"
  value       = aws_backup_plan.this.version
}

output "this" {
  value = aws_backup_plan.this
}
```

[top](#index)