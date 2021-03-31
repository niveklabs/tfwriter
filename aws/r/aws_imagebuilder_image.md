# aws_imagebuilder_image

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
module "aws_imagebuilder_image" {
  source = "./modules/aws/r/aws_imagebuilder_image"

  # distribution_configuration_arn - (optional) is a type of string
  distribution_configuration_arn = null
  # enhanced_image_metadata_enabled - (optional) is a type of bool
  enhanced_image_metadata_enabled = null
  # image_recipe_arn - (required) is a type of string
  image_recipe_arn = null
  # infrastructure_configuration_arn - (required) is a type of string
  infrastructure_configuration_arn = null
  # tags - (optional) is a type of map of string
  tags = {}

  image_tests_configuration = [{
    image_tests_enabled = null
    timeout_minutes     = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "image_tests_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      image_tests_enabled = bool
      timeout_minutes     = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_imagebuilder_image" "this" {
  distribution_configuration_arn   = var.distribution_configuration_arn
  enhanced_image_metadata_enabled  = var.enhanced_image_metadata_enabled
  image_recipe_arn                 = var.image_recipe_arn
  infrastructure_configuration_arn = var.infrastructure_configuration_arn
  tags                             = var.tags

  dynamic "image_tests_configuration" {
    for_each = var.image_tests_configuration
    content {
      image_tests_enabled = image_tests_configuration.value["image_tests_enabled"]
      timeout_minutes     = image_tests_configuration.value["timeout_minutes"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.arn
}

output "date_created" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.date_created
}

output "id" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.name
}

output "os_version" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.os_version
}

output "output_resources" {
  description = "returns a list of object"
  value       = aws_imagebuilder_image.this.output_resources
}

output "platform" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.platform
}

output "version" {
  description = "returns a string"
  value       = aws_imagebuilder_image.this.version
}

output "this" {
  value = aws_imagebuilder_image.this
}
```

[top](#index)