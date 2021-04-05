# signalfx_dashboard

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_dashboard" {
  source = "./modules/signalfx/r/signalfx_dashboard"

  # authorized_writer_teams - (optional) is a type of set of string
  authorized_writer_teams = []
  # authorized_writer_users - (optional) is a type of set of string
  authorized_writer_users = []
  # charts_resolution - (optional) is a type of string
  charts_resolution = null
  # dashboard_group - (required) is a type of string
  dashboard_group = null
  # description - (optional) is a type of string
  description = null
  # discovery_options_query - (optional) is a type of string
  discovery_options_query = null
  # discovery_options_selectors - (optional) is a type of set of string
  discovery_options_selectors = []
  # end_time - (optional) is a type of number
  end_time = null
  # name - (required) is a type of string
  name = null
  # start_time - (optional) is a type of number
  start_time = null
  # time_range - (optional) is a type of string
  time_range = null

  chart = [{
    chart_id = null
    column   = null
    height   = null
    row      = null
    width    = null
  }]

  column = [{
    chart_ids = []
    column    = null
    height    = null
    width     = null
  }]

  event_overlay = [{
    color  = null
    label  = null
    line   = null
    signal = null
    source = [{
      negated  = null
      property = null
      values   = []
    }]
    type = null
  }]

  filter = [{
    apply_if_exist = null
    negated        = null
    property       = null
    values         = []
  }]

  grid = [{
    chart_ids = []
    height    = null
    width     = null
  }]

  selected_event_overlay = [{
    signal = null
    source = [{
      negated  = null
      property = null
      values   = []
    }]
    type = null
  }]

  variable = [{
    alias                  = null
    apply_if_exist         = null
    description            = null
    property               = null
    replace_only           = null
    restricted_suggestions = null
    value_required         = null
    values                 = []
    values_suggested       = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorized_writer_teams" {
  description = "(optional) - Team IDs that have write access to this dashboard"
  type        = set(string)
  default     = null
}

variable "authorized_writer_users" {
  description = "(optional) - User IDs that have write access to this dashboard"
  type        = set(string)
  default     = null
}

variable "charts_resolution" {
  description = "(optional) - Specifies the chart data display resolution for charts in this dashboard. Value can be one of \"default\", \"low\", \"high\", or \"highest\". default by default"
  type        = string
  default     = null
}

variable "dashboard_group" {
  description = "(required) - The ID of the dashboard group that contains the dashboard. If an ID is not provided during creation, the dashboard will be placed in a newly created dashboard group"
  type        = string
}

variable "description" {
  description = "(optional) - Description of the dashboard (Optional)"
  type        = string
  default     = null
}

variable "discovery_options_query" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "discovery_options_selectors" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "end_time" {
  description = "(optional) - Seconds since epoch to end the visualization"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the dashboard"
  type        = string
}

variable "start_time" {
  description = "(optional) - Seconds since epoch to start the visualization"
  type        = number
  default     = null
}

variable "time_range" {
  description = "(optional) - From when to display data. SignalFx time syntax (e.g. -5m, -1h)"
  type        = string
  default     = null
}

variable "chart" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      chart_id = string
      column   = number
      height   = number
      row      = number
      width    = number
    }
  ))
  default = []
}

variable "column" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      chart_ids = list(string)
      column    = number
      height    = number
      width     = number
    }
  ))
  default = []
}

variable "event_overlay" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      color  = string
      label  = string
      line   = bool
      signal = string
      source = list(object(
        {
          negated  = bool
          property = string
          values   = set(string)
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      apply_if_exist = bool
      negated        = bool
      property       = string
      values         = set(string)
    }
  ))
  default = []
}

variable "grid" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      chart_ids = list(string)
      height    = number
      width     = number
    }
  ))
  default = []
}

variable "selected_event_overlay" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      signal = string
      source = list(object(
        {
          negated  = bool
          property = string
          values   = set(string)
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "variable" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      alias                  = string
      apply_if_exist         = bool
      description            = string
      property               = string
      replace_only           = bool
      restricted_suggestions = bool
      value_required         = bool
      values                 = set(string)
      values_suggested       = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_dashboard" "this" {
  authorized_writer_teams     = var.authorized_writer_teams
  authorized_writer_users     = var.authorized_writer_users
  charts_resolution           = var.charts_resolution
  dashboard_group             = var.dashboard_group
  description                 = var.description
  discovery_options_query     = var.discovery_options_query
  discovery_options_selectors = var.discovery_options_selectors
  end_time                    = var.end_time
  name                        = var.name
  start_time                  = var.start_time
  time_range                  = var.time_range

  dynamic "chart" {
    for_each = var.chart
    content {
      chart_id = chart.value["chart_id"]
      column   = chart.value["column"]
      height   = chart.value["height"]
      row      = chart.value["row"]
      width    = chart.value["width"]
    }
  }

  dynamic "column" {
    for_each = var.column
    content {
      chart_ids = column.value["chart_ids"]
      column    = column.value["column"]
      height    = column.value["height"]
      width     = column.value["width"]
    }
  }

  dynamic "event_overlay" {
    for_each = var.event_overlay
    content {
      color  = event_overlay.value["color"]
      label  = event_overlay.value["label"]
      line   = event_overlay.value["line"]
      signal = event_overlay.value["signal"]
      type   = event_overlay.value["type"]

      dynamic "source" {
        for_each = event_overlay.value.source
        content {
          negated  = source.value["negated"]
          property = source.value["property"]
          values   = source.value["values"]
        }
      }

    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      apply_if_exist = filter.value["apply_if_exist"]
      negated        = filter.value["negated"]
      property       = filter.value["property"]
      values         = filter.value["values"]
    }
  }

  dynamic "grid" {
    for_each = var.grid
    content {
      chart_ids = grid.value["chart_ids"]
      height    = grid.value["height"]
      width     = grid.value["width"]
    }
  }

  dynamic "selected_event_overlay" {
    for_each = var.selected_event_overlay
    content {
      signal = selected_event_overlay.value["signal"]
      type   = selected_event_overlay.value["type"]

      dynamic "source" {
        for_each = selected_event_overlay.value.source
        content {
          negated  = source.value["negated"]
          property = source.value["property"]
          values   = source.value["values"]
        }
      }

    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      alias                  = variable.value["alias"]
      apply_if_exist         = variable.value["apply_if_exist"]
      description            = variable.value["description"]
      property               = variable.value["property"]
      replace_only           = variable.value["replace_only"]
      restricted_suggestions = variable.value["restricted_suggestions"]
      value_required         = variable.value["value_required"]
      values                 = variable.value["values"]
      values_suggested       = variable.value["values_suggested"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_dashboard.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_dashboard.this.url
}

output "this" {
  value = signalfx_dashboard.this
}
```

[top](#index)