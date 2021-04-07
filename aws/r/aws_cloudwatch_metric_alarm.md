# aws_cloudwatch_metric_alarm

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
module "aws_cloudwatch_metric_alarm" {
  source = "./modules/aws/r/aws_cloudwatch_metric_alarm"

  # actions_enabled - (optional) is a type of bool
  actions_enabled = null
  # alarm_actions - (optional) is a type of set of string
  alarm_actions = []
  # alarm_description - (optional) is a type of string
  alarm_description = null
  # alarm_name - (required) is a type of string
  alarm_name = null
  # comparison_operator - (required) is a type of string
  comparison_operator = null
  # datapoints_to_alarm - (optional) is a type of number
  datapoints_to_alarm = null
  # dimensions - (optional) is a type of map of string
  dimensions = {}
  # evaluate_low_sample_count_percentiles - (optional) is a type of string
  evaluate_low_sample_count_percentiles = null
  # evaluation_periods - (required) is a type of number
  evaluation_periods = null
  # extended_statistic - (optional) is a type of string
  extended_statistic = null
  # insufficient_data_actions - (optional) is a type of set of string
  insufficient_data_actions = []
  # metric_name - (optional) is a type of string
  metric_name = null
  # namespace - (optional) is a type of string
  namespace = null
  # ok_actions - (optional) is a type of set of string
  ok_actions = []
  # period - (optional) is a type of number
  period = null
  # statistic - (optional) is a type of string
  statistic = null
  # tags - (optional) is a type of map of string
  tags = {}
  # threshold - (optional) is a type of number
  threshold = null
  # threshold_metric_id - (optional) is a type of string
  threshold_metric_id = null
  # treat_missing_data - (optional) is a type of string
  treat_missing_data = null
  # unit - (optional) is a type of string
  unit = null

  metric_query = [{
    expression = null
    id         = null
    label      = null
    metric = [{
      dimensions  = {}
      metric_name = null
      namespace   = null
      period      = null
      stat        = null
      unit        = null
    }]
    return_data = null
  }]
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

variable "comparison_operator" {
  description = "(required)"
  type        = string
}

variable "datapoints_to_alarm" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dimensions" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "evaluate_low_sample_count_percentiles" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "evaluation_periods" {
  description = "(required)"
  type        = number
}

variable "extended_statistic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "insufficient_data_actions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "metric_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ok_actions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "statistic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "threshold_metric_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "treat_missing_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metric_query" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      expression = string
      id         = string
      label      = string
      metric = list(object(
        {
          dimensions  = map(string)
          metric_name = string
          namespace   = string
          period      = number
          stat        = string
          unit        = string
        }
      ))
      return_data = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_metric_alarm" "this" {
  # actions_enabled - (optional) is a type of bool
  actions_enabled = var.actions_enabled
  # alarm_actions - (optional) is a type of set of string
  alarm_actions = var.alarm_actions
  # alarm_description - (optional) is a type of string
  alarm_description = var.alarm_description
  # alarm_name - (required) is a type of string
  alarm_name = var.alarm_name
  # comparison_operator - (required) is a type of string
  comparison_operator = var.comparison_operator
  # datapoints_to_alarm - (optional) is a type of number
  datapoints_to_alarm = var.datapoints_to_alarm
  # dimensions - (optional) is a type of map of string
  dimensions = var.dimensions
  # evaluate_low_sample_count_percentiles - (optional) is a type of string
  evaluate_low_sample_count_percentiles = var.evaluate_low_sample_count_percentiles
  # evaluation_periods - (required) is a type of number
  evaluation_periods = var.evaluation_periods
  # extended_statistic - (optional) is a type of string
  extended_statistic = var.extended_statistic
  # insufficient_data_actions - (optional) is a type of set of string
  insufficient_data_actions = var.insufficient_data_actions
  # metric_name - (optional) is a type of string
  metric_name = var.metric_name
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # ok_actions - (optional) is a type of set of string
  ok_actions = var.ok_actions
  # period - (optional) is a type of number
  period = var.period
  # statistic - (optional) is a type of string
  statistic = var.statistic
  # tags - (optional) is a type of map of string
  tags = var.tags
  # threshold - (optional) is a type of number
  threshold = var.threshold
  # threshold_metric_id - (optional) is a type of string
  threshold_metric_id = var.threshold_metric_id
  # treat_missing_data - (optional) is a type of string
  treat_missing_data = var.treat_missing_data
  # unit - (optional) is a type of string
  unit = var.unit

  dynamic "metric_query" {
    for_each = var.metric_query
    content {
      # expression - (optional) is a type of string
      expression = metric_query.value["expression"]
      # id - (required) is a type of string
      id = metric_query.value["id"]
      # label - (optional) is a type of string
      label = metric_query.value["label"]
      # return_data - (optional) is a type of bool
      return_data = metric_query.value["return_data"]

      dynamic "metric" {
        for_each = metric_query.value.metric
        content {
          # dimensions - (optional) is a type of map of string
          dimensions = metric.value["dimensions"]
          # metric_name - (required) is a type of string
          metric_name = metric.value["metric_name"]
          # namespace - (optional) is a type of string
          namespace = metric.value["namespace"]
          # period - (required) is a type of number
          period = metric.value["period"]
          # stat - (required) is a type of string
          stat = metric.value["stat"]
          # unit - (optional) is a type of string
          unit = metric.value["unit"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_metric_alarm.this.arn
}

output "evaluate_low_sample_count_percentiles" {
  description = "returns a string"
  value       = aws_cloudwatch_metric_alarm.this.evaluate_low_sample_count_percentiles
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_metric_alarm.this.id
}

output "this" {
  value = aws_cloudwatch_metric_alarm.this
}
```

[top](#index)