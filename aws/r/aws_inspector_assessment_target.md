# aws_inspector_assessment_target

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
module "aws_inspector_assessment_target" {
  source = "./modules/aws/r/aws_inspector_assessment_target"

  # name - (required) is a type of string
  name = null
  # resource_group_arn - (optional) is a type of string
  resource_group_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_arn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_inspector_assessment_target" "this" {
  name               = var.name
  resource_group_arn = var.resource_group_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_inspector_assessment_target.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_inspector_assessment_target.this.id
}

output "this" {
  value = aws_inspector_assessment_target.this
}
```

[top](#index)