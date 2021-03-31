# aws_imagebuilder_image_pipeline

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_imagebuilder_image_pipeline" {
  source = "./modules/aws/d/aws_imagebuilder_image_pipeline"

  # arn - (required) is a type of string
  arn = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_imagebuilder_image_pipeline" "this" {
  arn  = var.arn
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.date_created
}

output "date_last_run" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.date_last_run
}

output "date_next_run" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.date_next_run
}

output "date_updated" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.date_updated
}

output "description" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.description
}

output "distribution_configuration_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.distribution_configuration_arn
}

output "enhanced_image_metadata_enabled" {
  description = "returns a bool"
  value       = data.aws_imagebuilder_image_pipeline.this.enhanced_image_metadata_enabled
}

output "id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.id
}

output "image_recipe_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.image_recipe_arn
}

output "image_tests_configuration" {
  description = "returns a list of object"
  value       = data.aws_imagebuilder_image_pipeline.this.image_tests_configuration
}

output "infrastructure_configuration_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.infrastructure_configuration_arn
}

output "name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.name
}

output "platform" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.platform
}

output "schedule" {
  description = "returns a list of object"
  value       = data.aws_imagebuilder_image_pipeline.this.schedule
}

output "status" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_pipeline.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_imagebuilder_image_pipeline.this.tags
}

output "this" {
  value = aws_imagebuilder_image_pipeline.this
}
```

[top](#index)