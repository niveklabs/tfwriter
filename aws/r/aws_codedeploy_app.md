# aws_codedeploy_app

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_codedeploy_app" {
  source = "./modules/aws/r/aws_codedeploy_app"

  # compute_platform - (optional) is a type of string
  compute_platform = null
  # name - (required) is a type of string
  name = null
  # unique_id - (optional) is a type of string
  unique_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "unique_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_codedeploy_app" "this" {
  compute_platform = var.compute_platform
  name             = var.name
  unique_id        = var.unique_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_codedeploy_app.this.id
}

output "unique_id" {
  description = "returns a string"
  value       = aws_codedeploy_app.this.unique_id
}

output "this" {
  value = aws_codedeploy_app.this
}
```

[top](#index)