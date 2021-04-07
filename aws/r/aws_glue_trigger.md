# aws_glue_trigger

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
module "aws_glue_trigger" {
  source = "./modules/aws/r/aws_glue_trigger"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # schedule - (optional) is a type of string
  schedule = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
  # workflow_name - (optional) is a type of string
  workflow_name = null

  actions = [{
    arguments    = {}
    crawler_name = null
    job_name     = null
    notification_property = [{
      notify_delay_after = null
    }]
    security_configuration = null
    timeout                = null
  }]

  predicate = [{
    conditions = [{
      crawl_state      = null
      crawler_name     = null
      job_name         = null
      logical_operator = null
      state            = null
    }]
    logical = null
  }]

  timeouts = [{
    create = null
    delete = null
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

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "workflow_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "actions" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      arguments    = map(string)
      crawler_name = string
      job_name     = string
      notification_property = list(object(
        {
          notify_delay_after = number
        }
      ))
      security_configuration = string
      timeout                = number
    }
  ))
}

variable "predicate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      conditions = list(object(
        {
          crawl_state      = string
          crawler_name     = string
          job_name         = string
          logical_operator = string
          state            = string
        }
      ))
      logical = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_trigger" "this" {
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # schedule - (optional) is a type of string
  schedule = var.schedule
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
  # workflow_name - (optional) is a type of string
  workflow_name = var.workflow_name

  dynamic "actions" {
    for_each = var.actions
    content {
      # arguments - (optional) is a type of map of string
      arguments = actions.value["arguments"]
      # crawler_name - (optional) is a type of string
      crawler_name = actions.value["crawler_name"]
      # job_name - (optional) is a type of string
      job_name = actions.value["job_name"]
      # security_configuration - (optional) is a type of string
      security_configuration = actions.value["security_configuration"]
      # timeout - (optional) is a type of number
      timeout = actions.value["timeout"]

      dynamic "notification_property" {
        for_each = actions.value.notification_property
        content {
          # notify_delay_after - (optional) is a type of number
          notify_delay_after = notification_property.value["notify_delay_after"]
        }
      }

    }
  }

  dynamic "predicate" {
    for_each = var.predicate
    content {
      # logical - (optional) is a type of string
      logical = predicate.value["logical"]

      dynamic "conditions" {
        for_each = predicate.value.conditions
        content {
          # crawl_state - (optional) is a type of string
          crawl_state = conditions.value["crawl_state"]
          # crawler_name - (optional) is a type of string
          crawler_name = conditions.value["crawler_name"]
          # job_name - (optional) is a type of string
          job_name = conditions.value["job_name"]
          # logical_operator - (optional) is a type of string
          logical_operator = conditions.value["logical_operator"]
          # state - (optional) is a type of string
          state = conditions.value["state"]
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
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_trigger.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glue_trigger.this.id
}

output "state" {
  description = "returns a string"
  value       = aws_glue_trigger.this.state
}

output "this" {
  value = aws_glue_trigger.this
}
```

[top](#index)