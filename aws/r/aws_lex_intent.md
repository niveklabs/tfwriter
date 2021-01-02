# aws_lex_intent

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
module "aws_lex_intent" {
  source = "./modules/aws/r/aws_lex_intent"

  # create_version - (optional) is a type of bool
  create_version = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parent_intent_signature - (optional) is a type of string
  parent_intent_signature = null
  # sample_utterances - (optional) is a type of set of string
  sample_utterances = []

  conclusion_statement = [{
    message = [{
      content      = null
      content_type = null
      group_number = null
    }]
    response_card = null
  }]

  confirmation_prompt = [{
    max_attempts = null
    message = [{
      content      = null
      content_type = null
      group_number = null
    }]
    response_card = null
  }]

  dialog_code_hook = [{
    message_version = null
    uri             = null
  }]

  follow_up_prompt = [{
    prompt = [{
      max_attempts = null
      message = [{
        content      = null
        content_type = null
        group_number = null
      }]
      response_card = null
    }]
    rejection_statement = [{
      message = [{
        content      = null
        content_type = null
        group_number = null
      }]
      response_card = null
    }]
  }]

  fulfillment_activity = [{
    code_hook = [{
      message_version = null
      uri             = null
    }]
    type = null
  }]

  rejection_statement = [{
    message = [{
      content      = null
      content_type = null
      group_number = null
    }]
    response_card = null
  }]

  slot = [{
    description       = null
    name              = null
    priority          = null
    response_card     = null
    sample_utterances = []
    slot_constraint   = null
    slot_type         = null
    slot_type_version = null
    value_elicitation_prompt = [{
      max_attempts = null
      message = [{
        content      = null
        content_type = null
        group_number = null
      }]
      response_card = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_intent_signature" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sample_utterances" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "conclusion_statement" {
  description = "nested block: NestingList, min items: 0, max items: 1"
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
  default = []
}

variable "confirmation_prompt" {
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

variable "dialog_code_hook" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      message_version = string
      uri             = string
    }
  ))
  default = []
}

variable "follow_up_prompt" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      prompt = list(object(
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
      rejection_statement = list(object(
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
  ))
  default = []
}

variable "fulfillment_activity" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      code_hook = list(object(
        {
          message_version = string
          uri             = string
        }
      ))
      type = string
    }
  ))
}

variable "rejection_statement" {
  description = "nested block: NestingList, min items: 0, max items: 1"
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
  default = []
}

variable "slot" {
  description = "nested block: NestingSet, min items: 0, max items: 100"
  type = set(object(
    {
      description       = string
      name              = string
      priority          = number
      response_card     = string
      sample_utterances = list(string)
      slot_constraint   = string
      slot_type         = string
      slot_type_version = string
      value_elicitation_prompt = list(object(
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
resource "aws_lex_intent" "this" {
  create_version          = var.create_version
  description             = var.description
  name                    = var.name
  parent_intent_signature = var.parent_intent_signature
  sample_utterances       = var.sample_utterances

  dynamic "conclusion_statement" {
    for_each = var.conclusion_statement
    content {
      response_card = conclusion_statement.value["response_card"]

      dynamic "message" {
        for_each = conclusion_statement.value.message
        content {
          content      = message.value["content"]
          content_type = message.value["content_type"]
          group_number = message.value["group_number"]
        }
      }

    }
  }

  dynamic "confirmation_prompt" {
    for_each = var.confirmation_prompt
    content {
      max_attempts  = confirmation_prompt.value["max_attempts"]
      response_card = confirmation_prompt.value["response_card"]

      dynamic "message" {
        for_each = confirmation_prompt.value.message
        content {
          content      = message.value["content"]
          content_type = message.value["content_type"]
          group_number = message.value["group_number"]
        }
      }

    }
  }

  dynamic "dialog_code_hook" {
    for_each = var.dialog_code_hook
    content {
      message_version = dialog_code_hook.value["message_version"]
      uri             = dialog_code_hook.value["uri"]
    }
  }

  dynamic "follow_up_prompt" {
    for_each = var.follow_up_prompt
    content {

      dynamic "prompt" {
        for_each = follow_up_prompt.value.prompt
        content {
          max_attempts  = prompt.value["max_attempts"]
          response_card = prompt.value["response_card"]

          dynamic "message" {
            for_each = prompt.value.message
            content {
              content      = message.value["content"]
              content_type = message.value["content_type"]
              group_number = message.value["group_number"]
            }
          }

        }
      }

      dynamic "rejection_statement" {
        for_each = follow_up_prompt.value.rejection_statement
        content {
          response_card = rejection_statement.value["response_card"]

          dynamic "message" {
            for_each = rejection_statement.value.message
            content {
              content      = message.value["content"]
              content_type = message.value["content_type"]
              group_number = message.value["group_number"]
            }
          }

        }
      }

    }
  }

  dynamic "fulfillment_activity" {
    for_each = var.fulfillment_activity
    content {
      type = fulfillment_activity.value["type"]

      dynamic "code_hook" {
        for_each = fulfillment_activity.value.code_hook
        content {
          message_version = code_hook.value["message_version"]
          uri             = code_hook.value["uri"]
        }
      }

    }
  }

  dynamic "rejection_statement" {
    for_each = var.rejection_statement
    content {
      response_card = rejection_statement.value["response_card"]

      dynamic "message" {
        for_each = rejection_statement.value.message
        content {
          content      = message.value["content"]
          content_type = message.value["content_type"]
          group_number = message.value["group_number"]
        }
      }

    }
  }

  dynamic "slot" {
    for_each = var.slot
    content {
      description       = slot.value["description"]
      name              = slot.value["name"]
      priority          = slot.value["priority"]
      response_card     = slot.value["response_card"]
      sample_utterances = slot.value["sample_utterances"]
      slot_constraint   = slot.value["slot_constraint"]
      slot_type         = slot.value["slot_type"]
      slot_type_version = slot.value["slot_type_version"]

      dynamic "value_elicitation_prompt" {
        for_each = slot.value.value_elicitation_prompt
        content {
          max_attempts  = value_elicitation_prompt.value["max_attempts"]
          response_card = value_elicitation_prompt.value["response_card"]

          dynamic "message" {
            for_each = value_elicitation_prompt.value.message
            content {
              content      = message.value["content"]
              content_type = message.value["content_type"]
              group_number = message.value["group_number"]
            }
          }

        }
      }

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
  value       = aws_lex_intent.this.arn
}

output "checksum" {
  description = "returns a string"
  value       = aws_lex_intent.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = aws_lex_intent.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_lex_intent.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_lex_intent.this.last_updated_date
}

output "version" {
  description = "returns a string"
  value       = aws_lex_intent.this.version
}

output "this" {
  value = aws_lex_intent.this
}
```

[top](#index)