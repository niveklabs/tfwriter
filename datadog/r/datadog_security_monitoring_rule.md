# datadog_security_monitoring_rule

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_security_monitoring_rule" {
  source = "./modules/datadog/r/datadog_security_monitoring_rule"

  # enabled - (optional) is a type of bool
  enabled = null
  # message - (required) is a type of string
  message = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []

  case = [{
    condition     = null
    name          = null
    notifications = []
    status        = null
  }]

  options = [{
    evaluation_window   = null
    keep_alive          = null
    max_signal_duration = null
  }]

  query = [{
    aggregation     = null
    distinct_fields = []
    group_by_fields = []
    metric          = null
    name            = null
    query           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Whether the rule is enabled."
  type        = bool
  default     = null
}

variable "message" {
  description = "(required) - Message for generated signals."
  type        = string
}

variable "name" {
  description = "(required) - The name of the rule."
  type        = string
}

variable "tags" {
  description = "(optional) - Tags for generated signals."
  type        = list(string)
  default     = null
}

variable "case" {
  description = "nested block: NestingList, min items: 1, max items: 5"
  type = set(object(
    {
      condition     = string
      name          = string
      notifications = list(string)
      status        = string
    }
  ))
}

variable "options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      evaluation_window   = number
      keep_alive          = number
      max_signal_duration = number
    }
  ))
  default = []
}

variable "query" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      aggregation     = string
      distinct_fields = list(string)
      group_by_fields = list(string)
      metric          = string
      name            = string
      query           = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "datadog_security_monitoring_rule" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # message - (required) is a type of string
  message = var.message
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of list of string
  tags = var.tags

  dynamic "case" {
    for_each = var.case
    content {
      # condition - (optional) is a type of string
      condition = case.value["condition"]
      # name - (optional) is a type of string
      name = case.value["name"]
      # notifications - (optional) is a type of list of string
      notifications = case.value["notifications"]
      # status - (required) is a type of string
      status = case.value["status"]
    }
  }

  dynamic "options" {
    for_each = var.options
    content {
      # evaluation_window - (required) is a type of number
      evaluation_window = options.value["evaluation_window"]
      # keep_alive - (required) is a type of number
      keep_alive = options.value["keep_alive"]
      # max_signal_duration - (required) is a type of number
      max_signal_duration = options.value["max_signal_duration"]
    }
  }

  dynamic "query" {
    for_each = var.query
    content {
      # aggregation - (optional) is a type of string
      aggregation = query.value["aggregation"]
      # distinct_fields - (optional) is a type of list of string
      distinct_fields = query.value["distinct_fields"]
      # group_by_fields - (optional) is a type of list of string
      group_by_fields = query.value["group_by_fields"]
      # metric - (optional) is a type of string
      metric = query.value["metric"]
      # name - (optional) is a type of string
      name = query.value["name"]
      # query - (required) is a type of string
      query = query.value["query"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_security_monitoring_rule.this.id
}

output "this" {
  value = datadog_security_monitoring_rule.this
}
```

[top](#index)