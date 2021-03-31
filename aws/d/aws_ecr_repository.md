# aws_ecr_repository

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
module "aws_ecr_repository" {
  source = "./modules/aws/d/aws_ecr_repository"

  # name - (required) is a type of string
  name = null
  # registry_id - (optional) is a type of string
  registry_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "registry_id" {
  description = "(optional)"
  type        = string
  default     = null
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
data "aws_ecr_repository" "this" {
  name        = var.name
  registry_id = var.registry_id
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ecr_repository.this.arn
}

output "encryption_configuration" {
  description = "returns a list of object"
  value       = data.aws_ecr_repository.this.encryption_configuration
}

output "id" {
  description = "returns a string"
  value       = data.aws_ecr_repository.this.id
}

output "image_scanning_configuration" {
  description = "returns a list of object"
  value       = data.aws_ecr_repository.this.image_scanning_configuration
}

output "image_tag_mutability" {
  description = "returns a string"
  value       = data.aws_ecr_repository.this.image_tag_mutability
}

output "registry_id" {
  description = "returns a string"
  value       = data.aws_ecr_repository.this.registry_id
}

output "repository_url" {
  description = "returns a string"
  value       = data.aws_ecr_repository.this.repository_url
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ecr_repository.this.tags
}

output "this" {
  value = aws_ecr_repository.this
}
```

[top](#index)