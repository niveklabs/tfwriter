# aws_cloudwatch_composite_alarm

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
module "aws_cloudwatch_composite_alarm" {
  source = "./modules/aws/r/aws_cloudwatch_composite_alarm"

  # actions_enabled - (optional) is a type of bool
  actions_enabled = null
  # alarm_actions - (optional) is a type of set of string
  alarm_actions = []
  # alarm_description - (optional) is a type of string
  alarm_description = null
  # alarm_name - (required) is a type of string
  alarm_name = null
  # alarm_rule - (required) is a type of string
  alarm_rule = null
  # insufficient_data_actions - (optional) is a type of set of string
  insufficient_data_actions = []
  # ok_actions - (optional) is a type of set of string
  ok_actions = []
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "actions_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "alarm_actions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "alarm_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alarm_name" {
  description = "(required)"
  type        = string
}

variable "alarm_rule" {
  description = "(required)"
  type        = string
}

variable "insufficient_data_actions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ok_actions" {
  description = "(optional)"
  type        = set(string)
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
resource "aws_cloudwatch_composite_alarm" "this" {
  # actions_enabled - (optional) is a type of bool
  actions_enabled = var.actions_enabled
  # alarm_actions - (optional) is a type of set of string
  alarm_actions = var.alarm_actions
  # alarm_description - (optional) is a type of string
  alarm_description = var.alarm_description
  # alarm_name - (required) is a type of string
  alarm_name = var.alarm_name
  # alarm_rule - (required) is a type of string
  alarm_rule = var.alarm_rule
  # insufficient_data_actions - (optional) is a type of set of string
  insufficient_data_actions = var.insufficient_data_actions
  # ok_actions - (optional) is a type of set of string
  ok_actions = var.ok_actions
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_composite_alarm.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_composite_alarm.this.id
}

output "this" {
  value = aws_cloudwatch_composite_alarm.this
}
```

[top](#index)