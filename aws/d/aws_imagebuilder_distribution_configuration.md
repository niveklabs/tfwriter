# aws_imagebuilder_distribution_configuration

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_imagebuilder_distribution_configuration" {
  source = "./modules/aws/d/aws_imagebuilder_distribution_configuration"

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
data "aws_imagebuilder_distribution_configuration" "this" {
  arn  = var.arn
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = data.aws_imagebuilder_distribution_configuration.this.date_created
}

output "date_updated" {
  description = "returns a string"
  value       = data.aws_imagebuilder_distribution_configuration.this.date_updated
}

output "description" {
  description = "returns a string"
  value       = data.aws_imagebuilder_distribution_configuration.this.description
}

output "distribution" {
  description = "returns a set of object"
  value       = data.aws_imagebuilder_distribution_configuration.this.distribution
}

output "id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_distribution_configuration.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_distribution_configuration.this.name
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_imagebuilder_distribution_configuration.this.tags
}

output "this" {
  value = aws_imagebuilder_distribution_configuration.this
}
```

[top](#index)