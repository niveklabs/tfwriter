# aws_budgets_budget

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
module "aws_budgets_budget" {
  source = "./modules/aws/r/aws_budgets_budget"

  # account_id - (optional) is a type of string
  account_id = null
  # budget_type - (required) is a type of string
  budget_type = null
  # cost_filters - (optional) is a type of map of string
  cost_filters = {}
  # limit_amount - (required) is a type of string
  limit_amount = null
  # limit_unit - (required) is a type of string
  limit_unit = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # time_period_end - (optional) is a type of string
  time_period_end = null
  # time_period_start - (required) is a type of string
  time_period_start = null
  # time_unit - (required) is a type of string
  time_unit = null

  cost_types = [{
    include_credit             = null
    include_discount           = null
    include_other_subscription = null
    include_recurring          = null
    include_refund             = null
    include_subscription       = null
    include_support            = null
    include_tax                = null
    include_upfront            = null
    use_amortized              = null
    use_blended                = null
  }]

  notification = [{
    comparison_operator        = null
    notification_type          = null
    subscriber_email_addresses = []
    subscriber_sns_topic_arns  = []
    threshold                  = null
    threshold_type             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "budget_type" {
  description = "(required)"
  type        = string
}

variable "cost_filters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "limit_amount" {
  description = "(required)"
  type        = string
}

variable "limit_unit" {
  description = "(required)"
  type        = string
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

variable "time_period_end" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_period_start" {
  description = "(required)"
  type        = string
}

variable "time_unit" {
  description = "(required)"
  type        = string
}

variable "cost_types" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      include_credit             = bool
      include_discount           = bool
      include_other_subscription = bool
      include_recurring          = bool
      include_refund             = bool
      include_subscription       = bool
      include_support            = bool
      include_tax                = bool
      include_upfront            = bool
      use_amortized              = bool
      use_blended                = bool
    }
  ))
  default = []
}

variable "notification" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      comparison_operator        = string
      notification_type          = string
      subscriber_email_addresses = set(string)
      subscriber_sns_topic_arns  = set(string)
      threshold                  = number
      threshold_type             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_budgets_budget" "this" {
  account_id        = var.account_id
  budget_type       = var.budget_type
  cost_filters      = var.cost_filters
  limit_amount      = var.limit_amount
  limit_unit        = var.limit_unit
  name              = var.name
  name_prefix       = var.name_prefix
  time_period_end   = var.time_period_end
  time_period_start = var.time_period_start
  time_unit         = var.time_unit

  dynamic "cost_types" {
    for_each = var.cost_types
    content {
      include_credit             = cost_types.value["include_credit"]
      include_discount           = cost_types.value["include_discount"]
      include_other_subscription = cost_types.value["include_other_subscription"]
      include_recurring          = cost_types.value["include_recurring"]
      include_refund             = cost_types.value["include_refund"]
      include_subscription       = cost_types.value["include_subscription"]
      include_support            = cost_types.value["include_support"]
      include_tax                = cost_types.value["include_tax"]
      include_upfront            = cost_types.value["include_upfront"]
      use_amortized              = cost_types.value["use_amortized"]
      use_blended                = cost_types.value["use_blended"]
    }
  }

  dynamic "notification" {
    for_each = var.notification
    content {
      comparison_operator        = notification.value["comparison_operator"]
      notification_type          = notification.value["notification_type"]
      subscriber_email_addresses = notification.value["subscriber_email_addresses"]
      subscriber_sns_topic_arns  = notification.value["subscriber_sns_topic_arns"]
      threshold                  = notification.value["threshold"]
      threshold_type             = notification.value["threshold_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = aws_budgets_budget.this.account_id
}

output "cost_filters" {
  description = "returns a map of string"
  value       = aws_budgets_budget.this.cost_filters
}

output "id" {
  description = "returns a string"
  value       = aws_budgets_budget.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_budgets_budget.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_budgets_budget.this.name_prefix
}

output "this" {
  value = aws_budgets_budget.this
}
```

[top](#index)