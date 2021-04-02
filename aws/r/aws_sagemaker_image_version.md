# aws_sagemaker_image_version

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_sagemaker_image_version" {
  source = "./modules/aws/r/aws_sagemaker_image_version"

  # base_image - (required) is a type of string
  base_image = null
  # image_name - (required) is a type of string
  image_name = null
}
```

[top](#index)

### Variables

```terraform
variable "base_image" {
  description = "(required)"
  type        = string
}

variable "image_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_image_version" "this" {
  base_image = var.base_image
  image_name = var.image_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_image_version.this.arn
}

output "container_image" {
  description = "returns a string"
  value       = aws_sagemaker_image_version.this.container_image
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_image_version.this.id
}

output "image_arn" {
  description = "returns a string"
  value       = aws_sagemaker_image_version.this.image_arn
}

output "version" {
  description = "returns a number"
  value       = aws_sagemaker_image_version.this.version
}

output "this" {
  value = aws_sagemaker_image_version.this
}
```

[top](#index)