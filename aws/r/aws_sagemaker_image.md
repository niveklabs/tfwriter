# aws_sagemaker_image

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
module "aws_sagemaker_image" {
  source = "./modules/aws/r/aws_sagemaker_image"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # image_name - (required) is a type of string
  image_name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
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

### Resource

```terraform
resource "aws_sagemaker_image" "this" {
  description  = var.description
  display_name = var.display_name
  image_name   = var.image_name
  role_arn     = var.role_arn
  tags         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_image.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_image.this.id
}

output "this" {
  value = aws_sagemaker_image.this
}
```

[top](#index)