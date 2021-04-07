# aws_ecr_image

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ecr_image" {
  source = "./modules/aws/d/aws_ecr_image"

  # image_digest - (optional) is a type of string
  image_digest = null
  # image_tag - (optional) is a type of string
  image_tag = null
  # registry_id - (optional) is a type of string
  registry_id = null
  # repository_name - (required) is a type of string
  repository_name = null
}
```

[top](#index)

### Variables

```terraform
variable "image_digest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "registry_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_ecr_image" "this" {
  # image_digest - (optional) is a type of string
  image_digest = var.image_digest
  # image_tag - (optional) is a type of string
  image_tag = var.image_tag
  # registry_id - (optional) is a type of string
  registry_id = var.registry_id
  # repository_name - (required) is a type of string
  repository_name = var.repository_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_ecr_image.this.id
}

output "image_digest" {
  description = "returns a string"
  value       = data.aws_ecr_image.this.image_digest
}

output "image_pushed_at" {
  description = "returns a number"
  value       = data.aws_ecr_image.this.image_pushed_at
}

output "image_size_in_bytes" {
  description = "returns a number"
  value       = data.aws_ecr_image.this.image_size_in_bytes
}

output "image_tags" {
  description = "returns a list of string"
  value       = data.aws_ecr_image.this.image_tags
}

output "registry_id" {
  description = "returns a string"
  value       = data.aws_ecr_image.this.registry_id
}

output "this" {
  value = aws_ecr_image.this
}
```

[top](#index)