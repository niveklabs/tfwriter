# aws_lex_bot

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lex_bot" {
  source = "./modules/aws/r/aws_lex_bot"

  # child_directed - (required) is a type of bool
  child_directed = null
  # create_version - (optional) is a type of bool
  create_version = null
  # description - (optional) is a type of string
  description = null
  # detect_sentiment - (optional) is a type of bool
  detect_sentiment = null
  # enable_model_improvements - (optional) is a type of bool
  enable_model_improvements = null
  # idle_session_ttl_in_seconds - (optional) is a type of number
  idle_session_ttl_in_seconds = null
  # locale - (optional) is a type of string
  locale = null
  # name - (required) is a type of string
  name = null
  # nlu_intent_confidence_threshold - (optional) is a type of number
  nlu_intent_confidence_threshold = null
  # process_behavior - (optional) is a type of string
  process_behavior = null
  # voice_id - (optional) is a type of string
  voice_id = null

  abort_statement = [{
    message = [{
      content      = null
      content_type = null
      group_number = null
    }]
    response_card = null
  }]

  clarification_prompt = [{
    max_attempts = null
    message = [{
      content      = null
      content_type = null
      group_number = null
    }]
    response_card = null
  }]

  intent = [{
    intent_name    = null
    intent_version = null
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
variable "child_directed" {
  description = "(required)"
  type        = bool
}

variable "create_version" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "detect_sentiment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_model_improvements" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "idle_session_ttl_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "locale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nlu_intent_confidence_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "process_behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voice_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "abort_statement" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      message = set(object(
        {
          content      = string
          content_type = string
          group_number = number
        }
      ))
      response_card = string
    }
  ))
}

variable "clarification_prompt" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_attempts = number
      message = set(object(
        {
          content      = string
          content_type = string
          group_number = number
        }
      ))
      response_card = string
    }
  ))
  default = []
}

variable "intent" {
  description = "nested block: NestingSet, min items: 1, max items: 100"
  type = set(object(
    {
      intent_name    = string
      intent_version = string
    }
  ))
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
resource "aws_lex_bot" "this" {
  child_directed                  = var.child_directed
  create_version                  = var.create_version
  description                     = var.description
  detect_sentiment                = var.detect_sentiment
  enable_model_improvements       = var.enable_model_improvements
  idle_session_ttl_in_seconds     = var.idle_session_ttl_in_seconds
  locale                          = var.locale
  name                            = var.name
  nlu_intent_confidence_threshold = var.nlu_intent_confidence_threshold
  process_behavior                = var.process_behavior
  voice_id                        = var.voice_id

  dynamic "abort_statement" {
    for_each = var.abort_statement
    content {
      response_card = abort_statement.value["response_card"]

      dynamic "message" {
        for_each = abort_statement.value.message
        content {
          content      = message.value["content"]
          content_type = message.value["content_type"]
          group_number = message.value["group_number"]
        }
      }

    }
  }

  dynamic "clarification_prompt" {
    for_each = var.clarification_prompt
    content {
      max_attempts  = clarification_prompt.value["max_attempts"]
      response_card = clarification_prompt.value["response_card"]

      dynamic "message" {
        for_each = clarification_prompt.value.message
        content {
          content      = message.value["content"]
          content_type = message.value["content_type"]
          group_number = message.value["group_number"]
        }
      }

    }
  }

  dynamic "intent" {
    for_each = var.intent
    content {
      intent_name    = intent.value["intent_name"]
      intent_version = intent.value["intent_version"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = aws_lex_bot.this.arn
}

output "checksum" {
  description = "returns a string"
  value       = aws_lex_bot.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = aws_lex_bot.this.created_date
}

output "failure_reason" {
  description = "returns a string"
  value       = aws_lex_bot.this.failure_reason
}

output "id" {
  description = "returns a string"
  value       = aws_lex_bot.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_lex_bot.this.last_updated_date
}

output "status" {
  description = "returns a string"
  value       = aws_lex_bot.this.status
}

output "version" {
  description = "returns a string"
  value       = aws_lex_bot.this.version
}

output "voice_id" {
  description = "returns a string"
  value       = aws_lex_bot.this.voice_id
}

output "this" {
  value = aws_lex_bot.this
}
```

[top](#index)