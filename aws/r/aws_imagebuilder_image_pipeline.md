# aws_imagebuilder_image_pipeline

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_imagebuilder_image_pipeline" {
  source = "./modules/aws/r/aws_imagebuilder_image_pipeline"

  # description - (optional) is a type of string
  description = null
  # distribution_configuration_arn - (optional) is a type of string
  distribution_configuration_arn = null
  # enhanced_image_metadata_enabled - (optional) is a type of bool
  enhanced_image_metadata_enabled = null
  # image_recipe_arn - (required) is a type of string
  image_recipe_arn = null
  # infrastructure_configuration_arn - (required) is a type of string
  infrastructure_configuration_arn = null
  # name - (required) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}

  image_tests_configuration = [{
    image_tests_enabled = null
    timeout_minutes     = null
  }]

  schedule = [{
    pipeline_execution_start_condition = null
    schedule_expression                = null
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

variable "distribution_configuration_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enhanced_image_metadata_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "image_recipe_arn" {
  description = "(required)"
  type        = string
}

variable "infrastructure_configuration_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "image_tests_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      image_tests_enabled = bool
      timeout_minutes     = number
    }
  ))
  default = []
}

variable "schedule" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      pipeline_execution_start_condition = string
      schedule_expression                = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_imagebuilder_image_pipeline" "this" {
  description                      = var.description
  distribution_configuration_arn   = var.distribution_configuration_arn
  enhanced_image_metadata_enabled  = var.enhanced_image_metadata_enabled
  image_recipe_arn                 = var.image_recipe_arn
  infrastructure_configuration_arn = var.infrastructure_configuration_arn
  name                             = var.name
  status                           = var.status
  tags                             = var.tags

  dynamic "image_tests_configuration" {
    for_each = var.image_tests_configuration
    content {
      image_tests_enabled = image_tests_configuration.value["image_tests_enabled"]
      timeout_minutes     = image_tests_configuration.value["timeout_minutes"]
    }
  }

  dynamic "schedule" {
    for_each = var.schedule
    content {
      pipeline_execution_start_condition = schedule.value["pipeline_execution_start_condition"]
      schedule_expression                = schedule.value["schedule_expression"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.arn
}

output "date_created" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.date_created
}

output "date_last_run" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.date_last_run
}

output "date_next_run" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.date_next_run
}

output "date_updated" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.date_updated
}

output "id" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.id
}

output "platform" {
  description = "returns a string"
  value       = aws_imagebuilder_image_pipeline.this.platform
}

output "this" {
  value = aws_imagebuilder_image_pipeline.this
}
```

[top](#index)