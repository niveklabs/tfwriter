# datadog_service_level_objective

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
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_service_level_objective" {
  source = "./modules/datadog/r/datadog_service_level_objective"

  # description - (optional) is a type of string
  description = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # groups - (optional) is a type of set of string
  groups = []
  # monitor_ids - (optional) is a type of set of number
  monitor_ids = []
  # monitor_search - (optional) is a type of string
  monitor_search = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
  # type - (required) is a type of string
  type = null
  # validate - (optional) is a type of bool
  validate = null

  query = [{
    denominator = null
    numerator   = null
  }]

  thresholds = [{
    target          = null
    target_display  = null
    timeframe       = null
    warning         = null
    warning_display = null
  }]
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

variable "force_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "groups" {
  description = "(optional) - A static set of groups to filter monitor-based SLOs"
  type        = set(string)
  default     = null
}

variable "monitor_ids" {
  description = "(optional) - A static set of monitor IDs to use as part of the SLO"
  type        = set(number)
  default     = null
}

variable "monitor_search" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "validate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "query" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      denominator = string
      numerator   = string
    }
  ))
  default = []
}

variable "thresholds" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      target          = number
      target_display  = string
      timeframe       = string
      warning         = number
      warning_display = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "datadog_service_level_objective" "this" {
  description    = var.description
  force_delete   = var.force_delete
  groups         = var.groups
  monitor_ids    = var.monitor_ids
  monitor_search = var.monitor_search
  name           = var.name
  tags           = var.tags
  type           = var.type
  validate       = var.validate

  dynamic "query" {
    for_each = var.query
    content {
      denominator = query.value["denominator"]
      numerator   = query.value["numerator"]
    }
  }

  dynamic "thresholds" {
    for_each = var.thresholds
    content {
      target          = thresholds.value["target"]
      target_display  = thresholds.value["target_display"]
      timeframe       = thresholds.value["timeframe"]
      warning         = thresholds.value["warning"]
      warning_display = thresholds.value["warning_display"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_service_level_objective.this.id
}

output "monitor_search" {
  description = "returns a string"
  value       = datadog_service_level_objective.this.monitor_search
}

output "this" {
  value = datadog_service_level_objective.this
}
```

[top](#index)