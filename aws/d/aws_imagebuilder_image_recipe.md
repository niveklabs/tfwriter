# aws_imagebuilder_image_recipe

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
module "aws_imagebuilder_image_recipe" {
  source = "./modules/aws/d/aws_imagebuilder_image_recipe"

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
data "aws_imagebuilder_image_recipe" "this" {
  arn  = var.arn
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "block_device_mapping" {
  description = "returns a set of object"
  value       = data.aws_imagebuilder_image_recipe.this.block_device_mapping
}

output "component" {
  description = "returns a list of object"
  value       = data.aws_imagebuilder_image_recipe.this.component
}

output "date_created" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.date_created
}

output "description" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.name
}

output "owner" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.owner
}

output "parent_image" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.parent_image
}

output "platform" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.platform
}

output "version" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.version
}

output "working_directory" {
  description = "returns a string"
  value       = data.aws_imagebuilder_image_recipe.this.working_directory
}

output "this" {
  value = aws_imagebuilder_image_recipe.this
}
```

[top](#index)