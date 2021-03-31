# newrelic_dashboard

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_dashboard" {
  source = "./modules/newrelic/r/newrelic_dashboard"

  # editable - (optional) is a type of string
  editable = null
  # grid_column_count - (optional) is a type of number
  grid_column_count = null
  # icon - (optional) is a type of string
  icon = null
  # title - (required) is a type of string
  title = null
  # visibility - (optional) is a type of string
  visibility = null

  filter = [{
    attributes  = []
    event_types = []
  }]

  widget = [{
    account_id = null
    column     = null
    compare_with = [{
      offset_duration = null
      presentation = [{
        color = null
        name  = null
      }]
    }]
    drilldown_dashboard_id = null
    duration               = null
    end_time               = null
    entity_ids             = []
    facet                  = null
    height                 = null
    limit                  = null
    metric = [{
      name   = null
      scope  = null
      units  = null
      values = []
    }]
    notes            = null
    nrql             = null
    order_by         = null
    raw_metric_name  = null
    row              = null
    source           = null
    threshold_red    = null
    threshold_yellow = null
    title            = null
    visualization    = null
    widget_id        = null
    width            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "editable" {
  description = "(optional) - Determines who can edit the dashboard in an account. Valid values are all, editable_by_all, editable_by_owner, or read_only. Defaults to editable_by_all."
  type        = string
  default     = null
}

variable "grid_column_count" {
  description = "(optional) - New Relic One supports a 3 column grid or a 12 column grid. New Relic Insights supports a 3 column grid."
  type        = number
  default     = null
}

variable "icon" {
  description = "(optional) - The icon for the dashboard."
  type        = string
  default     = null
}

variable "title" {
  description = "(required) - The title of the dashboard."
  type        = string
}

variable "visibility" {
  description = "(optional) - Determines who can see the dashboard in an account. Valid values are all or owner. Defaults to all."
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attributes  = set(string)
      event_types = set(string)
    }
  ))
  default = []
}

variable "widget" {
  description = "nested block: NestingSet, min items: 0, max items: 300"
  type = set(object(
    {
      account_id = number
      column     = number
      compare_with = set(object(
        {
          offset_duration = string
          presentation = list(object(
            {
              color = string
              name  = string
            }
          ))
        }
      ))
      drilldown_dashboard_id = number
      duration               = number
      end_time               = number
      entity_ids             = set(number)
      facet                  = string
      height                 = number
      limit                  = number
      metric = set(object(
        {
          name   = string
          scope  = string
          units  = string
          values = set(string)
        }
      ))
      notes            = string
      nrql             = string
      order_by         = string
      raw_metric_name  = string
      row              = number
      source           = string
      threshold_red    = number
      threshold_yellow = number
      title            = string
      visualization    = string
      widget_id        = number
      width            = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_dashboard" "this" {
  editable          = var.editable
  grid_column_count = var.grid_column_count
  icon              = var.icon
  title             = var.title
  visibility        = var.visibility

  dynamic "filter" {
    for_each = var.filter
    content {
      attributes  = filter.value["attributes"]
      event_types = filter.value["event_types"]
    }
  }

  dynamic "widget" {
    for_each = var.widget
    content {
      account_id             = widget.value["account_id"]
      column                 = widget.value["column"]
      drilldown_dashboard_id = widget.value["drilldown_dashboard_id"]
      duration               = widget.value["duration"]
      end_time               = widget.value["end_time"]
      entity_ids             = widget.value["entity_ids"]
      facet                  = widget.value["facet"]
      height                 = widget.value["height"]
      limit                  = widget.value["limit"]
      notes                  = widget.value["notes"]
      nrql                   = widget.value["nrql"]
      order_by               = widget.value["order_by"]
      row                    = widget.value["row"]
      source                 = widget.value["source"]
      threshold_red          = widget.value["threshold_red"]
      threshold_yellow       = widget.value["threshold_yellow"]
      title                  = widget.value["title"]
      visualization          = widget.value["visualization"]
      width                  = widget.value["width"]

      dynamic "compare_with" {
        for_each = widget.value.compare_with
        content {
          offset_duration = compare_with.value["offset_duration"]

          dynamic "presentation" {
            for_each = compare_with.value.presentation
            content {
              color = presentation.value["color"]
              name  = presentation.value["name"]
            }
          }

        }
      }

      dynamic "metric" {
        for_each = widget.value.metric
        content {
          name   = metric.value["name"]
          scope  = metric.value["scope"]
          units  = metric.value["units"]
          values = metric.value["values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dashboard_url" {
  description = "returns a string"
  value       = newrelic_dashboard.this.dashboard_url
}

output "id" {
  description = "returns a string"
  value       = newrelic_dashboard.this.id
}

output "this" {
  value = newrelic_dashboard.this
}
```

[top](#index)