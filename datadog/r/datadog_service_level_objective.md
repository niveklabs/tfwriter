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
    datadog = ">= 2.24.0"
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
  description = "(optional) - A description of this service level objective."
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional) - A boolean indicating whether this monitor can be deleted even if it’s referenced by other resources (e.g. dashboards)."
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
  description = "(required) - Name of Datadog service level objective"
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tags to associate with your service level objective. This can help you categorize and filter service level objectives in the service level objectives page of the UI. Note: it's not currently possible to filter by these tags when querying via the API"
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(required) - The type of the service level objective. The mapping from these types to the types found in the Datadog Web UI can be found in the Datadog API [documentation page](https://docs.datadoghq.com/api/v1/service-level-objectives/#create-a-slo-object). Available options to choose from are: `metric` and `monitor`."
  type        = string
}

variable "validate" {
  description = "(optional) - Whether or not to validate the SLO."
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
  # description - (optional) is a type of string
  description = var.description
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # groups - (optional) is a type of set of string
  groups = var.groups
  # monitor_ids - (optional) is a type of set of number
  monitor_ids = var.monitor_ids
  # monitor_search - (optional) is a type of string
  monitor_search = var.monitor_search
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
  # validate - (optional) is a type of bool
  validate = var.validate

  dynamic "query" {
    for_each = var.query
    content {
      # denominator - (required) is a type of string
      denominator = query.value["denominator"]
      # numerator - (required) is a type of string
      numerator = query.value["numerator"]
    }
  }

  dynamic "thresholds" {
    for_each = var.thresholds
    content {
      # target - (required) is a type of number
      target = thresholds.value["target"]
      # target_display - (optional) is a type of string
      target_display = thresholds.value["target_display"]
      # timeframe - (required) is a type of string
      timeframe = thresholds.value["timeframe"]
      # warning - (optional) is a type of number
      warning = thresholds.value["warning"]
      # warning_display - (optional) is a type of string
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