# aws_lambda_event_source_mapping

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
module "aws_lambda_event_source_mapping" {
  source = "./modules/aws/r/aws_lambda_event_source_mapping"

  # batch_size - (optional) is a type of number
  batch_size = null
  # bisect_batch_on_function_error - (optional) is a type of bool
  bisect_batch_on_function_error = null
  # enabled - (optional) is a type of bool
  enabled = null
  # event_source_arn - (required) is a type of string
  event_source_arn = null
  # function_name - (required) is a type of string
  function_name = null
  # maximum_batching_window_in_seconds - (optional) is a type of number
  maximum_batching_window_in_seconds = null
  # maximum_record_age_in_seconds - (optional) is a type of number
  maximum_record_age_in_seconds = null
  # maximum_retry_attempts - (optional) is a type of number
  maximum_retry_attempts = null
  # parallelization_factor - (optional) is a type of number
  parallelization_factor = null
  # starting_position - (optional) is a type of string
  starting_position = null
  # starting_position_timestamp - (optional) is a type of string
  starting_position_timestamp = null
  # topics - (optional) is a type of set of string
  topics = []

  destination_config = [{
    on_failure = [{
      destination_arn = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "batch_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bisect_batch_on_function_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "event_source_arn" {
  description = "(required)"
  type        = string
}

variable "function_name" {
  description = "(required)"
  type        = string
}

variable "maximum_batching_window_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_record_age_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_retry_attempts" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "parallelization_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "starting_position" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "starting_position_timestamp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topics" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      on_failure = list(object(
        {
          destination_arn = string
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
resource "aws_lambda_event_source_mapping" "this" {
  batch_size                         = var.batch_size
  bisect_batch_on_function_error     = var.bisect_batch_on_function_error
  enabled                            = var.enabled
  event_source_arn                   = var.event_source_arn
  function_name                      = var.function_name
  maximum_batching_window_in_seconds = var.maximum_batching_window_in_seconds
  maximum_record_age_in_seconds      = var.maximum_record_age_in_seconds
  maximum_retry_attempts             = var.maximum_retry_attempts
  parallelization_factor             = var.parallelization_factor
  starting_position                  = var.starting_position
  starting_position_timestamp        = var.starting_position_timestamp
  topics                             = var.topics

  dynamic "destination_config" {
    for_each = var.destination_config
    content {

      dynamic "on_failure" {
        for_each = destination_config.value.on_failure
        content {
          destination_arn = on_failure.value["destination_arn"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "function_arn" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.function_arn
}

output "id" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.last_modified
}

output "last_processing_result" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.last_processing_result
}

output "maximum_record_age_in_seconds" {
  description = "returns a number"
  value       = aws_lambda_event_source_mapping.this.maximum_record_age_in_seconds
}

output "maximum_retry_attempts" {
  description = "returns a number"
  value       = aws_lambda_event_source_mapping.this.maximum_retry_attempts
}

output "parallelization_factor" {
  description = "returns a number"
  value       = aws_lambda_event_source_mapping.this.parallelization_factor
}

output "state" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.state
}

output "state_transition_reason" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.state_transition_reason
}

output "uuid" {
  description = "returns a string"
  value       = aws_lambda_event_source_mapping.this.uuid
}

output "this" {
  value = aws_lambda_event_source_mapping.this
}
```

[top](#index)