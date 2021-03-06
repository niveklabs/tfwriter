# aws_ssm_maintenance_window_task

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
module "aws_ssm_maintenance_window_task" {
  source = "./modules/aws/r/aws_ssm_maintenance_window_task"

  # description - (optional) is a type of string
  description = null
  # max_concurrency - (required) is a type of string
  max_concurrency = null
  # max_errors - (required) is a type of string
  max_errors = null
  # name - (optional) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # service_role_arn - (optional) is a type of string
  service_role_arn = null
  # task_arn - (required) is a type of string
  task_arn = null
  # task_type - (required) is a type of string
  task_type = null
  # window_id - (required) is a type of string
  window_id = null

  targets = [{
    key    = null
    values = []
  }]

  task_invocation_parameters = [{
    automation_parameters = [{
      document_version = null
      parameter = [{
        name   = null
        values = []
      }]
    }]
    lambda_parameters = [{
      client_context = null
      payload        = null
      qualifier      = null
    }]
    run_command_parameters = [{
      cloudwatch_config = [{
        cloudwatch_log_group_name = null
        cloudwatch_output_enabled = null
      }]
      comment            = null
      document_hash      = null
      document_hash_type = null
      document_version   = null
      notification_config = [{
        notification_arn    = null
        notification_events = []
        notification_type   = null
      }]
      output_s3_bucket     = null
      output_s3_key_prefix = null
      parameter = [{
        name   = null
        values = []
      }]
      service_role_arn = null
      timeout_seconds  = null
    }]
    step_functions_parameters = [{
      input = null
      name  = null
    }]
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

variable "max_concurrency" {
  description = "(required)"
  type        = string
}

variable "max_errors" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "task_arn" {
  description = "(required)"
  type        = string
}

variable "task_type" {
  description = "(required)"
  type        = string
}

variable "window_id" {
  description = "(required)"
  type        = string
}

variable "targets" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      key    = string
      values = list(string)
    }
  ))
  default = []
}

variable "task_invocation_parameters" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      automation_parameters = list(object(
        {
          document_version = string
          parameter = set(object(
            {
              name   = string
              values = list(string)
            }
          ))
        }
      ))
      lambda_parameters = list(object(
        {
          client_context = string
          payload        = string
          qualifier      = string
        }
      ))
      run_command_parameters = list(object(
        {
          cloudwatch_config = list(object(
            {
              cloudwatch_log_group_name = string
              cloudwatch_output_enabled = bool
            }
          ))
          comment            = string
          document_hash      = string
          document_hash_type = string
          document_version   = string
          notification_config = list(object(
            {
              notification_arn    = string
              notification_events = list(string)
              notification_type   = string
            }
          ))
          output_s3_bucket     = string
          output_s3_key_prefix = string
          parameter = set(object(
            {
              name   = string
              values = list(string)
            }
          ))
          service_role_arn = string
          timeout_seconds  = number
        }
      ))
      step_functions_parameters = list(object(
        {
          input = string
          name  = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_maintenance_window_task" "this" {
  # description - (optional) is a type of string
  description = var.description
  # max_concurrency - (required) is a type of string
  max_concurrency = var.max_concurrency
  # max_errors - (required) is a type of string
  max_errors = var.max_errors
  # name - (optional) is a type of string
  name = var.name
  # priority - (optional) is a type of number
  priority = var.priority
  # service_role_arn - (optional) is a type of string
  service_role_arn = var.service_role_arn
  # task_arn - (required) is a type of string
  task_arn = var.task_arn
  # task_type - (required) is a type of string
  task_type = var.task_type
  # window_id - (required) is a type of string
  window_id = var.window_id

  dynamic "targets" {
    for_each = var.targets
    content {
      # key - (required) is a type of string
      key = targets.value["key"]
      # values - (required) is a type of list of string
      values = targets.value["values"]
    }
  }

  dynamic "task_invocation_parameters" {
    for_each = var.task_invocation_parameters
    content {

      dynamic "automation_parameters" {
        for_each = task_invocation_parameters.value.automation_parameters
        content {
          # document_version - (optional) is a type of string
          document_version = automation_parameters.value["document_version"]

          dynamic "parameter" {
            for_each = automation_parameters.value.parameter
            content {
              # name - (required) is a type of string
              name = parameter.value["name"]
              # values - (required) is a type of list of string
              values = parameter.value["values"]
            }
          }

        }
      }

      dynamic "lambda_parameters" {
        for_each = task_invocation_parameters.value.lambda_parameters
        content {
          # client_context - (optional) is a type of string
          client_context = lambda_parameters.value["client_context"]
          # payload - (optional) is a type of string
          payload = lambda_parameters.value["payload"]
          # qualifier - (optional) is a type of string
          qualifier = lambda_parameters.value["qualifier"]
        }
      }

      dynamic "run_command_parameters" {
        for_each = task_invocation_parameters.value.run_command_parameters
        content {
          # comment - (optional) is a type of string
          comment = run_command_parameters.value["comment"]
          # document_hash - (optional) is a type of string
          document_hash = run_command_parameters.value["document_hash"]
          # document_hash_type - (optional) is a type of string
          document_hash_type = run_command_parameters.value["document_hash_type"]
          # document_version - (optional) is a type of string
          document_version = run_command_parameters.value["document_version"]
          # output_s3_bucket - (optional) is a type of string
          output_s3_bucket = run_command_parameters.value["output_s3_bucket"]
          # output_s3_key_prefix - (optional) is a type of string
          output_s3_key_prefix = run_command_parameters.value["output_s3_key_prefix"]
          # service_role_arn - (optional) is a type of string
          service_role_arn = run_command_parameters.value["service_role_arn"]
          # timeout_seconds - (optional) is a type of number
          timeout_seconds = run_command_parameters.value["timeout_seconds"]

          dynamic "cloudwatch_config" {
            for_each = run_command_parameters.value.cloudwatch_config
            content {
              # cloudwatch_log_group_name - (optional) is a type of string
              cloudwatch_log_group_name = cloudwatch_config.value["cloudwatch_log_group_name"]
              # cloudwatch_output_enabled - (optional) is a type of bool
              cloudwatch_output_enabled = cloudwatch_config.value["cloudwatch_output_enabled"]
            }
          }

          dynamic "notification_config" {
            for_each = run_command_parameters.value.notification_config
            content {
              # notification_arn - (optional) is a type of string
              notification_arn = notification_config.value["notification_arn"]
              # notification_events - (optional) is a type of list of string
              notification_events = notification_config.value["notification_events"]
              # notification_type - (optional) is a type of string
              notification_type = notification_config.value["notification_type"]
            }
          }

          dynamic "parameter" {
            for_each = run_command_parameters.value.parameter
            content {
              # name - (required) is a type of string
              name = parameter.value["name"]
              # values - (required) is a type of list of string
              values = parameter.value["values"]
            }
          }

        }
      }

      dynamic "step_functions_parameters" {
        for_each = task_invocation_parameters.value.step_functions_parameters
        content {
          # input - (optional) is a type of string
          input = step_functions_parameters.value["input"]
          # name - (optional) is a type of string
          name = step_functions_parameters.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssm_maintenance_window_task.this.id
}

output "service_role_arn" {
  description = "returns a string"
  value       = aws_ssm_maintenance_window_task.this.service_role_arn
}

output "this" {
  value = aws_ssm_maintenance_window_task.this
}
```

[top](#index)