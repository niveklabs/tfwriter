# aws_lex_bot_alias

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
module "aws_lex_bot_alias" {
  source = "./modules/aws/r/aws_lex_bot_alias"

  # bot_name - (required) is a type of string
  bot_name = null
  # bot_version - (required) is a type of string
  bot_version = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  conversation_logs = [{
    iam_role_arn = null
    log_settings = [{
      destination     = null
      kms_key_arn     = null
      log_type        = null
      resource_arn    = null
      resource_prefix = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bot_name" {
  description = "(required)"
  type        = string
}

variable "bot_version" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "conversation_logs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      iam_role_arn = string
      log_settings = set(object(
        {
          destination     = string
          kms_key_arn     = string
          log_type        = string
          resource_arn    = string
          resource_prefix = string
        }
      ))
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lex_bot_alias" "this" {
  # bot_name - (required) is a type of string
  bot_name = var.bot_name
  # bot_version - (required) is a type of string
  bot_version = var.bot_version
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "conversation_logs" {
    for_each = var.conversation_logs
    content {
      # iam_role_arn - (required) is a type of string
      iam_role_arn = conversation_logs.value["iam_role_arn"]

      dynamic "log_settings" {
        for_each = conversation_logs.value.log_settings
        content {
          # destination - (required) is a type of string
          destination = log_settings.value["destination"]
          # kms_key_arn - (optional) is a type of string
          kms_key_arn = log_settings.value["kms_key_arn"]
          # log_type - (required) is a type of string
          log_type = log_settings.value["log_type"]
          # resource_arn - (required) is a type of string
          resource_arn = log_settings.value["resource_arn"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lex_bot_alias.this.arn
}

output "checksum" {
  description = "returns a string"
  value       = aws_lex_bot_alias.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = aws_lex_bot_alias.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_lex_bot_alias.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_lex_bot_alias.this.last_updated_date
}

output "this" {
  value = aws_lex_bot_alias.this
}
```

[top](#index)