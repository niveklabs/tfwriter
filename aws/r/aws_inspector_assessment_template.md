# aws_inspector_assessment_template

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
module "aws_inspector_assessment_template" {
  source = "./modules/aws/r/aws_inspector_assessment_template"

  # duration - (required) is a type of number
  duration = null
  # name - (required) is a type of string
  name = null
  # rules_package_arns - (required) is a type of set of string
  rules_package_arns = []
  # tags - (optional) is a type of map of string
  tags = {}
  # target_arn - (required) is a type of string
  target_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "duration" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rules_package_arns" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_inspector_assessment_template" "this" {
  # duration - (required) is a type of number
  duration = var.duration
  # name - (required) is a type of string
  name = var.name
  # rules_package_arns - (required) is a type of set of string
  rules_package_arns = var.rules_package_arns
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target_arn - (required) is a type of string
  target_arn = var.target_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_inspector_assessment_template.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_inspector_assessment_template.this.id
}

output "this" {
  value = aws_inspector_assessment_template.this
}
```

[top](#index)