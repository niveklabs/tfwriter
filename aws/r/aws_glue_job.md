# aws_glue_job

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
module "aws_glue_job" {
  source = "./modules/aws/r/aws_glue_job"

  # connections - (optional) is a type of list of string
  connections = []
  # default_arguments - (optional) is a type of map of string
  default_arguments = {}
  # description - (optional) is a type of string
  description = null
  # glue_version - (optional) is a type of string
  glue_version = null
  # max_capacity - (optional) is a type of number
  max_capacity = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # name - (required) is a type of string
  name = null
  # non_overridable_arguments - (optional) is a type of map of string
  non_overridable_arguments = {}
  # number_of_workers - (optional) is a type of number
  number_of_workers = null
  # role_arn - (required) is a type of string
  role_arn = null
  # security_configuration - (optional) is a type of string
  security_configuration = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timeout - (optional) is a type of number
  timeout = null
  # worker_type - (optional) is a type of string
  worker_type = null

  command = [{
    name            = null
    python_version  = null
    script_location = null
  }]

  execution_property = [{
    max_concurrent_runs = null
  }]

  notification_property = [{
    notify_delay_after = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connections" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "default_arguments" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "glue_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "non_overridable_arguments" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "number_of_workers" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "security_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "command" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      name            = string
      python_version  = string
      script_location = string
    }
  ))
}

variable "execution_property" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_concurrent_runs = number
    }
  ))
  default = []
}

variable "notification_property" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      notify_delay_after = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_job" "this" {
  connections               = var.connections
  default_arguments         = var.default_arguments
  description               = var.description
  glue_version              = var.glue_version
  max_capacity              = var.max_capacity
  max_retries               = var.max_retries
  name                      = var.name
  non_overridable_arguments = var.non_overridable_arguments
  number_of_workers         = var.number_of_workers
  role_arn                  = var.role_arn
  security_configuration    = var.security_configuration
  tags                      = var.tags
  timeout                   = var.timeout
  worker_type               = var.worker_type

  dynamic "command" {
    for_each = var.command
    content {
      name            = command.value["name"]
      python_version  = command.value["python_version"]
      script_location = command.value["script_location"]
    }
  }

  dynamic "execution_property" {
    for_each = var.execution_property
    content {
      max_concurrent_runs = execution_property.value["max_concurrent_runs"]
    }
  }

  dynamic "notification_property" {
    for_each = var.notification_property
    content {
      notify_delay_after = notification_property.value["notify_delay_after"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_job.this.arn
}

output "glue_version" {
  description = "returns a string"
  value       = aws_glue_job.this.glue_version
}

output "id" {
  description = "returns a string"
  value       = aws_glue_job.this.id
}

output "max_capacity" {
  description = "returns a number"
  value       = aws_glue_job.this.max_capacity
}

output "this" {
  value = aws_glue_job.this
}
```

[top](#index)