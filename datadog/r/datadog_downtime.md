# datadog_downtime

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
module "datadog_downtime" {
  source = "./modules/datadog/r/datadog_downtime"

  # active - (optional) is a type of bool
  active = null
  # disabled - (optional) is a type of bool
  disabled = null
  # end - (optional) is a type of number
  end = null
  # end_date - (optional) is a type of string
  end_date = null
  # message - (optional) is a type of string
  message = null
  # monitor_id - (optional) is a type of number
  monitor_id = null
  # monitor_tags - (optional) is a type of set of string
  monitor_tags = []
  # scope - (required) is a type of list of string
  scope = []
  # start - (optional) is a type of number
  start = null
  # start_date - (optional) is a type of string
  start_date = null
  # timezone - (optional) is a type of string
  timezone = null

  recurrence = [{
    period            = null
    rrule             = null
    type              = null
    until_date        = null
    until_occurrences = null
    week_days         = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional) - When true indicates this downtime is being actively applied"
  type        = bool
  default     = null
}

variable "disabled" {
  description = "(optional) - When true indicates this downtime is not being applied"
  type        = bool
  default     = null
}

variable "end" {
  description = "(optional) - Optionally specify an end date when this downtime should expire"
  type        = number
  default     = null
}

variable "end_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "message" {
  description = "(optional) - An optional message to provide when creating the downtime, can include notification handles"
  type        = string
  default     = null
}

variable "monitor_id" {
  description = "(optional) - When specified, this downtime will only apply to this monitor"
  type        = number
  default     = null
}

variable "monitor_tags" {
  description = "(optional) - A list of monitor tags (up to 25), i.e. tags that are applied directly to monitors to which the downtime applies"
  type        = set(string)
  default     = null
}

variable "scope" {
  description = "(required) - specify the group scope to which this downtime applies. For everything use '*'"
  type        = list(string)
}

variable "start" {
  description = "(optional) - Specify when this downtime should start"
  type        = number
  default     = null
}

variable "start_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional) - The timezone for the downtime, default UTC"
  type        = string
  default     = null
}

variable "recurrence" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      period            = number
      rrule             = string
      type              = string
      until_date        = number
      until_occurrences = number
      week_days         = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_downtime" "this" {
  active       = var.active
  disabled     = var.disabled
  end          = var.end
  end_date     = var.end_date
  message      = var.message
  monitor_id   = var.monitor_id
  monitor_tags = var.monitor_tags
  scope        = var.scope
  start        = var.start
  start_date   = var.start_date
  timezone     = var.timezone

  dynamic "recurrence" {
    for_each = var.recurrence
    content {
      period            = recurrence.value["period"]
      rrule             = recurrence.value["rrule"]
      type              = recurrence.value["type"]
      until_date        = recurrence.value["until_date"]
      until_occurrences = recurrence.value["until_occurrences"]
      week_days         = recurrence.value["week_days"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_downtime.this.id
}

output "this" {
  value = datadog_downtime.this
}
```

[top](#index)