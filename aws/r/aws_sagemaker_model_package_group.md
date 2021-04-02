# aws_sagemaker_model_package_group

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
module "aws_sagemaker_model_package_group" {
  source = "./modules/aws/r/aws_sagemaker_model_package_group"

  # model_package_group_description - (optional) is a type of string
  model_package_group_description = null
  # model_package_group_name - (required) is a type of string
  model_package_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "model_package_group_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "model_package_group_name" {
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
resource "aws_sagemaker_model_package_group" "this" {
  model_package_group_description = var.model_package_group_description
  model_package_group_name        = var.model_package_group_name
  tags                            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_model_package_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_model_package_group.this.id
}

output "this" {
  value = aws_sagemaker_model_package_group.this
}
```

[top](#index)