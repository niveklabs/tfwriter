# aws_cloudwatch_event_target

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
module "aws_cloudwatch_event_target" {
  source = "./modules/aws/r/aws_cloudwatch_event_target"

  # arn - (required) is a type of string
  arn = null
  # event_bus_name - (optional) is a type of string
  event_bus_name = null
  # input - (optional) is a type of string
  input = null
  # input_path - (optional) is a type of string
  input_path = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # rule - (required) is a type of string
  rule = null
  # target_id - (optional) is a type of string
  target_id = null

  batch_target = [{
    array_size     = null
    job_attempts   = null
    job_definition = null
    job_name       = null
  }]

  dead_letter_config = [{
    arn = null
  }]

  ecs_target = [{
    group       = null
    launch_type = null
    network_configuration = [{
      assign_public_ip = null
      security_groups  = []
      subnets          = []
    }]
    platform_version    = null
    task_count          = null
    task_definition_arn = null
  }]

  input_transformer = [{
    input_paths    = {}
    input_template = null
  }]

  kinesis_target = [{
    partition_key_path = null
  }]

  retry_policy = [{
    maximum_event_age_in_seconds = null
    maximum_retry_attempts       = null
  }]

  run_command_targets = [{
    key    = null
    values = []
  }]

  sqs_target = [{
    message_group_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "event_bus_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule" {
  description = "(required)"
  type        = string
}

variable "target_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "batch_target" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      array_size     = number
      job_attempts   = number
      job_definition = string
      job_name       = string
    }
  ))
  default = []
}

variable "dead_letter_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arn = string
    }
  ))
  default = []
}

variable "ecs_target" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group       = string
      launch_type = string
      network_configuration = list(object(
        {
          assign_public_ip = bool
          security_groups  = set(string)
          subnets          = set(string)
        }
      ))
      platform_version    = string
      task_count          = number
      task_definition_arn = string
    }
  ))
  default = []
}

variable "input_transformer" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      input_paths    = map(string)
      input_template = string
    }
  ))
  default = []
}

variable "kinesis_target" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      partition_key_path = string
    }
  ))
  default = []
}

variable "retry_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      maximum_event_age_in_seconds = number
      maximum_retry_attempts       = number
    }
  ))
  default = []
}

variable "run_command_targets" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      key    = string
      values = list(string)
    }
  ))
  default = []
}

variable "sqs_target" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      message_group_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_event_target" "this" {
  arn            = var.arn
  event_bus_name = var.event_bus_name
  input          = var.input
  input_path     = var.input_path
  role_arn       = var.role_arn
  rule           = var.rule
  target_id      = var.target_id

  dynamic "batch_target" {
    for_each = var.batch_target
    content {
      array_size     = batch_target.value["array_size"]
      job_attempts   = batch_target.value["job_attempts"]
      job_definition = batch_target.value["job_definition"]
      job_name       = batch_target.value["job_name"]
    }
  }

  dynamic "dead_letter_config" {
    for_each = var.dead_letter_config
    content {
      arn = dead_letter_config.value["arn"]
    }
  }

  dynamic "ecs_target" {
    for_each = var.ecs_target
    content {
      group               = ecs_target.value["group"]
      launch_type         = ecs_target.value["launch_type"]
      platform_version    = ecs_target.value["platform_version"]
      task_count          = ecs_target.value["task_count"]
      task_definition_arn = ecs_target.value["task_definition_arn"]

      dynamic "network_configuration" {
        for_each = ecs_target.value.network_configuration
        content {
          assign_public_ip = network_configuration.value["assign_public_ip"]
          security_groups  = network_configuration.value["security_groups"]
          subnets          = network_configuration.value["subnets"]
        }
      }

    }
  }

  dynamic "input_transformer" {
    for_each = var.input_transformer
    content {
      input_paths    = input_transformer.value["input_paths"]
      input_template = input_transformer.value["input_template"]
    }
  }

  dynamic "kinesis_target" {
    for_each = var.kinesis_target
    content {
      partition_key_path = kinesis_target.value["partition_key_path"]
    }
  }

  dynamic "retry_policy" {
    for_each = var.retry_policy
    content {
      maximum_event_age_in_seconds = retry_policy.value["maximum_event_age_in_seconds"]
      maximum_retry_attempts       = retry_policy.value["maximum_retry_attempts"]
    }
  }

  dynamic "run_command_targets" {
    for_each = var.run_command_targets
    content {
      key    = run_command_targets.value["key"]
      values = run_command_targets.value["values"]
    }
  }

  dynamic "sqs_target" {
    for_each = var.sqs_target
    content {
      message_group_id = sqs_target.value["message_group_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_event_target.this.id
}

output "target_id" {
  description = "returns a string"
  value       = aws_cloudwatch_event_target.this.target_id
}

output "this" {
  value = aws_cloudwatch_event_target.this
}
```

[top](#index)