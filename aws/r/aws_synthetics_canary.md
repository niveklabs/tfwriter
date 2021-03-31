# aws_synthetics_canary

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_synthetics_canary" {
  source = "./modules/aws/r/aws_synthetics_canary"

  # artifact_s3_location - (required) is a type of string
  artifact_s3_location = null
  # execution_role_arn - (required) is a type of string
  execution_role_arn = null
  # failure_retention_period - (optional) is a type of number
  failure_retention_period = null
  # handler - (required) is a type of string
  handler = null
  # name - (required) is a type of string
  name = null
  # runtime_version - (required) is a type of string
  runtime_version = null
  # s3_bucket - (optional) is a type of string
  s3_bucket = null
  # s3_key - (optional) is a type of string
  s3_key = null
  # s3_version - (optional) is a type of string
  s3_version = null
  # start_canary - (optional) is a type of bool
  start_canary = null
  # success_retention_period - (optional) is a type of number
  success_retention_period = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zip_file - (optional) is a type of string
  zip_file = null

  run_config = [{
    active_tracing     = null
    memory_in_mb       = null
    timeout_in_seconds = null
  }]

  schedule = [{
    duration_in_seconds = null
    expression          = null
  }]

  vpc_config = [{
    security_group_ids = []
    subnet_ids         = []
    vpc_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "artifact_s3_location" {
  description = "(required)"
  type        = string
}

variable "execution_role_arn" {
  description = "(required)"
  type        = string
}

variable "failure_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "handler" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "runtime_version" {
  description = "(required)"
  type        = string
}

variable "s3_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_canary" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "success_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zip_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "run_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      active_tracing     = bool
      memory_in_mb       = number
      timeout_in_seconds = number
    }
  ))
  default = []
}

variable "schedule" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      duration_in_seconds = number
      expression          = string
    }
  ))
}

variable "vpc_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group_ids = set(string)
      subnet_ids         = set(string)
      vpc_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_synthetics_canary" "this" {
  artifact_s3_location     = var.artifact_s3_location
  execution_role_arn       = var.execution_role_arn
  failure_retention_period = var.failure_retention_period
  handler                  = var.handler
  name                     = var.name
  runtime_version          = var.runtime_version
  s3_bucket                = var.s3_bucket
  s3_key                   = var.s3_key
  s3_version               = var.s3_version
  start_canary             = var.start_canary
  success_retention_period = var.success_retention_period
  tags                     = var.tags
  zip_file                 = var.zip_file

  dynamic "run_config" {
    for_each = var.run_config
    content {
      active_tracing     = run_config.value["active_tracing"]
      memory_in_mb       = run_config.value["memory_in_mb"]
      timeout_in_seconds = run_config.value["timeout_in_seconds"]
    }
  }

  dynamic "schedule" {
    for_each = var.schedule
    content {
      duration_in_seconds = schedule.value["duration_in_seconds"]
      expression          = schedule.value["expression"]
    }
  }

  dynamic "vpc_config" {
    for_each = var.vpc_config
    content {
      security_group_ids = vpc_config.value["security_group_ids"]
      subnet_ids         = vpc_config.value["subnet_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_synthetics_canary.this.arn
}

output "engine_arn" {
  description = "returns a string"
  value       = aws_synthetics_canary.this.engine_arn
}

output "id" {
  description = "returns a string"
  value       = aws_synthetics_canary.this.id
}

output "source_location_arn" {
  description = "returns a string"
  value       = aws_synthetics_canary.this.source_location_arn
}

output "status" {
  description = "returns a string"
  value       = aws_synthetics_canary.this.status
}

output "timeline" {
  description = "returns a list of object"
  value       = aws_synthetics_canary.this.timeline
}

output "this" {
  value = aws_synthetics_canary.this
}
```

[top](#index)