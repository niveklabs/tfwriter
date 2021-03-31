# aws_imagebuilder_image

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
module "aws_imagebuilder_image" {
  source = "./modules/aws/d/aws_imagebuilder_image"

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
data "aws_imagebuilder_image" "this" {
  arn  = var.arn
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "build_version_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.build_version_arn
}

output "date_created" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.date_created
}

output "distribution_configuration_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.distribution_configuration_arn
}

output "enhanced_image_metadata_enabled" {
  description = "returns a bool"
  value       = data.aws_imagebuilder_image.this.enhanced_image_metadata_enabled
}

output "id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.id
}

output "image_recipe_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.image_recipe_arn
}

output "image_tests_configuration" {
  description = "returns a list of object"
  value       = data.aws_imagebuilder_image.this.image_tests_configuration
}

output "infrastructure_configuration_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.infrastructure_configuration_arn
}

output "name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.name
}

output "os_version" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.os_version
}

output "output_resources" {
  description = "returns a list of object"
  value       = data.aws_imagebuilder_image.this.output_resources
}

output "platform" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.platform
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_imagebuilder_image.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image.this.version
}

output "this" {
  value = aws_imagebuilder_image.this
}
```

[top](#index)