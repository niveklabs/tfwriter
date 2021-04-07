# aws_sagemaker_prebuilt_ecr_image

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
module "aws_sagemaker_prebuilt_ecr_image" {
  source = "./modules/aws/d/aws_sagemaker_prebuilt_ecr_image"

  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # image_tag - (optional) is a type of string
  image_tag = null
  # region - (optional) is a type of string
  region = null
  # repository_name - (required) is a type of string
  repository_name = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_suffix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
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
data "aws_sagemaker_prebuilt_ecr_image" "this" {
  # dns_suffix - (optional) is a type of string
  dns_suffix = var.dns_suffix
  # image_tag - (optional) is a type of string
  image_tag = var.image_tag
  # region - (optional) is a type of string
  region = var.region
  # repository_name - (required) is a type of string
  repository_name = var.repository_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_sagemaker_prebuilt_ecr_image.this.id
}

output "registry_id" {
  description = "returns a string"
  value       = data.aws_sagemaker_prebuilt_ecr_image.this.registry_id
}

output "registry_path" {
  description = "returns a string"
  value       = data.aws_sagemaker_prebuilt_ecr_image.this.registry_path
}

output "this" {
  value = aws_sagemaker_prebuilt_ecr_image.this
}
```

[top](#index)