# aws_batch_job_definition

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
module "aws_batch_job_definition" {
  source = "./modules/aws/r/aws_batch_job_definition"

  # container_properties - (optional) is a type of string
  container_properties = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null

  retry_strategy = [{
    attempts = null
  }]

  timeout = [{
    attempt_duration_seconds = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "container_properties" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
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

variable "retry_strategy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attempts = number
    }
  ))
  default = []
}

variable "timeout" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attempt_duration_seconds = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_batch_job_definition" "this" {
  container_properties = var.container_properties
  name                 = var.name
  parameters           = var.parameters
  tags                 = var.tags
  type                 = var.type

  dynamic "retry_strategy" {
    for_each = var.retry_strategy
    content {
      attempts = retry_strategy.value["attempts"]
    }
  }

  dynamic "timeout" {
    for_each = var.timeout
    content {
      attempt_duration_seconds = timeout.value["attempt_duration_seconds"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_batch_job_definition.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_batch_job_definition.this.id
}

output "revision" {
  description = "returns a number"
  value       = aws_batch_job_definition.this.revision
}

output "this" {
  value = aws_batch_job_definition.this
}
```

[top](#index)