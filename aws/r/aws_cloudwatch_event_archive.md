# aws_cloudwatch_event_archive

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
module "aws_cloudwatch_event_archive" {
  source = "./modules/aws/r/aws_cloudwatch_event_archive"

  # description - (optional) is a type of string
  description = null
  # event_pattern - (optional) is a type of string
  event_pattern = null
  # event_source_arn - (required) is a type of string
  event_source_arn = null
  # name - (required) is a type of string
  name = null
  # retention_days - (optional) is a type of number
  retention_days = null
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

variable "event_pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_source_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_event_archive" "this" {
  description      = var.description
  event_pattern    = var.event_pattern
  event_source_arn = var.event_source_arn
  name             = var.name
  retention_days   = var.retention_days
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_event_archive.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_event_archive.this.id
}

output "this" {
  value = aws_cloudwatch_event_archive.this
}
```

[top](#index)