# aws_appautoscaling_scheduled_action

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
module "aws_appautoscaling_scheduled_action" {
  source = "./modules/aws/r/aws_appautoscaling_scheduled_action"

  # end_time - (optional) is a type of string
  end_time = null
  # name - (required) is a type of string
  name = null
  # resource_id - (required) is a type of string
  resource_id = null
  # scalable_dimension - (required) is a type of string
  scalable_dimension = null
  # schedule - (required) is a type of string
  schedule = null
  # service_namespace - (required) is a type of string
  service_namespace = null
  # start_time - (optional) is a type of string
  start_time = null
  # timezone - (optional) is a type of string
  timezone = null

  scalable_target_action = [{
    max_capacity = null
    min_capacity = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "scalable_dimension" {
  description = "(required)"
  type        = string
}

variable "schedule" {
  description = "(required)"
  type        = string
}

variable "service_namespace" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scalable_target_action" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      max_capacity = string
      min_capacity = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_appautoscaling_scheduled_action" "this" {
  end_time           = var.end_time
  name               = var.name
  resource_id        = var.resource_id
  scalable_dimension = var.scalable_dimension
  schedule           = var.schedule
  service_namespace  = var.service_namespace
  start_time         = var.start_time
  timezone           = var.timezone

  dynamic "scalable_target_action" {
    for_each = var.scalable_target_action
    content {
      max_capacity = scalable_target_action.value["max_capacity"]
      min_capacity = scalable_target_action.value["min_capacity"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_appautoscaling_scheduled_action.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_appautoscaling_scheduled_action.this.id
}

output "this" {
  value = aws_appautoscaling_scheduled_action.this
}
```

[top](#index)