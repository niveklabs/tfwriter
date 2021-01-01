# aws_glue_trigger
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
```hcl
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
  description = "nested mode: NestingList, min items: 1, max items: 0"
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
```hcl
resource "aws_glue_trigger" "this" {
  description   = var.description
  enabled       = var.enabled
  name          = var.name
  schedule      = var.schedule
  tags          = var.tags
  type          = var.type
  workflow_name = var.workflow_name

  dynamic "actions" {
    for_each = var.actions
    content {
      arguments              = actions.value["arguments"]
      crawler_name           = actions.value["crawler_name"]
      job_name               = actions.value["job_name"]
      security_configuration = actions.value["security_configuration"]
      timeout                = actions.value["timeout"]

      dynamic "notification_property" {
        for_each = actions.value.notification_property
        content {
          notify_delay_after = notification_property.value["notify_delay_after"]
        }
      }

    }
  }

  dynamic "predicate" {
    for_each = var.predicate
    content {
      logical = predicate.value["logical"]

      dynamic "conditions" {
        for_each = predicate.value.conditions
        content {
          crawl_state      = conditions.value["crawl_state"]
          crawler_name     = conditions.value["crawler_name"]
          job_name         = conditions.value["job_name"]
          logical_operator = conditions.value["logical_operator"]
          state            = conditions.value["state"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_glue_trigger.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glue_trigger.this.id
}

output "this" {
  value = aws_glue_trigger.this
}
```
[top](#index)
