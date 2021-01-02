# aws_sagemaker_notebook_instance_lifecycle_configuration

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_sagemaker_notebook_instance_lifecycle_configuration" {
  source = "./modules/aws/r/aws_sagemaker_notebook_instance_lifecycle_configuration"

  # name - (optional) is a type of string
  name = null
  # on_create - (optional) is a type of string
  on_create = null
  # on_start - (optional) is a type of string
  on_start = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "on_create" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "on_start" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_notebook_instance_lifecycle_configuration" "this" {
  name      = var.name
  on_create = var.on_create
  on_start  = var.on_start
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_notebook_instance_lifecycle_configuration.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_notebook_instance_lifecycle_configuration.this.id
}

output "this" {
  value = aws_sagemaker_notebook_instance_lifecycle_configuration.this
}
```

[top](#index)