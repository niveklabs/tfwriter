# aws_cloudwatch_event_rule

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
module "aws_cloudwatch_event_rule" {
  source = "./modules/aws/r/aws_cloudwatch_event_rule"

  # description - (optional) is a type of string
  description = null
  # event_bus_name - (optional) is a type of string
  event_bus_name = null
  # event_pattern - (optional) is a type of string
  event_pattern = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # schedule_expression - (optional) is a type of string
  schedule_expression = null
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

variable "event_bus_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_expression" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "aws_cloudwatch_event_rule" "this" {
  description         = var.description
  event_bus_name      = var.event_bus_name
  event_pattern       = var.event_pattern
  is_enabled          = var.is_enabled
  name                = var.name
  name_prefix         = var.name_prefix
  role_arn            = var.role_arn
  schedule_expression = var.schedule_expression
  tags                = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_event_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_event_rule.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_cloudwatch_event_rule.this.name
}

output "this" {
  value = aws_cloudwatch_event_rule.this
}
```

[top](#index)