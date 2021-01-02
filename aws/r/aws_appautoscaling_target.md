# aws_appautoscaling_target

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
module "aws_appautoscaling_target" {
  source = "./modules/aws/r/aws_appautoscaling_target"

  # max_capacity - (required) is a type of number
  max_capacity = null
  # min_capacity - (required) is a type of number
  min_capacity = null
  # resource_id - (required) is a type of string
  resource_id = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # scalable_dimension - (required) is a type of string
  scalable_dimension = null
  # service_namespace - (required) is a type of string
  service_namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "max_capacity" {
  description = "(required)"
  type        = number
}

variable "min_capacity" {
  description = "(required)"
  type        = number
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scalable_dimension" {
  description = "(required)"
  type        = string
}

variable "service_namespace" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_appautoscaling_target" "this" {
  max_capacity       = var.max_capacity
  min_capacity       = var.min_capacity
  resource_id        = var.resource_id
  role_arn           = var.role_arn
  scalable_dimension = var.scalable_dimension
  service_namespace  = var.service_namespace
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_appautoscaling_target.this.id
}

output "role_arn" {
  description = "returns a string"
  value       = aws_appautoscaling_target.this.role_arn
}

output "this" {
  value = aws_appautoscaling_target.this
}
```

[top](#index)