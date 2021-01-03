# datadog_screenboard

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
module "datadog_screenboard" {
  source = "./modules/datadog/r/datadog_screenboard"

  # height - (optional) is a type of string
  height = null
  # read_only - (optional) is a type of bool
  read_only = null
  # shared - (optional) is a type of bool
  shared = null
  # title - (required) is a type of string
  title = null
  # width - (optional) is a type of string
  width = null

  template_variable = [{
    default = null
    name    = null
    prefix  = null
  }]

  widget = [{
    alert_id                  = null
    auto_refresh              = null
    bgcolor                   = null
    check                     = null
    color                     = null
    color_preference          = null
    columns                   = null
    display_format            = null
    env                       = null
    event_size                = null
    font_size                 = null
    group                     = null
    group_by                  = []
    grouping                  = null
    height                    = null
    hide_zero_counts          = null
    html                      = null
    layout_version            = null
    legend                    = null
    legend_size               = null
    logset                    = null
    manage_status_show_title  = null
    manage_status_title_align = null
    manage_status_title_size  = null
    manage_status_title_text  = null
    margin                    = null
    monitor                   = {}
    must_show_breakdown       = null
    must_show_distribution    = null
    must_show_errors          = null
    must_show_hits            = null
    must_show_latency         = null
    must_show_resource_list   = null
    params                    = {}
    precision                 = null
    query                     = null
    rule = [{
      color     = null
      threshold = null
      timeframe = null
    }]
    service_name        = null
    service_service     = null
    show_last_triggered = null
    size_version        = null
    sizing              = null
    summary_type        = null
    tags                = []
    text                = null
    text_align          = null
    text_size           = null
    tick                = null
    tick_edge           = null
    tick_pos            = null
    tile_def = [{
      autoscale   = null
      custom_unit = null
      event = [{
        q = null
      }]
      group = []
      marker = [{
        label = null
        type  = null
        value = null
      }]
      no_group_hosts  = null
      no_metric_hosts = null
      node_type       = null
      precision       = null
      request = [{
        aggregator = null
        apm_query = [{
          compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          search = [{
            query = null
          }]
        }]
        change_type = null
        compare_to  = null
        conditional_format = [{
          color           = null
          comparator      = null
          custom_bg_color = null
          invert          = null
          palette         = null
          value           = null
        }]
        extra_col     = null
        increase_good = null
        limit         = null
        log_query = [{
          compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          search = [{
            query = null
          }]
        }]
        metadata_json = null
        metric        = null
        order_by      = null
        order_dir     = null
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q           = null
        query_type  = null
        style       = {}
        tag_filters = []
        text_filter = null
        type        = null
      }]
      scope      = []
      style      = {}
      text_align = null
      viz        = null
    }]
    time        = {}
    timeframes  = []
    title       = null
    title_align = null
    title_size  = null
    type        = null
    unit        = null
    url         = null
    viz_type    = null
    width       = null
    x           = null
    y           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "height" {
  description = "(optional) - Height of the screenboard"
  type        = string
  default     = null
}

variable "read_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shared" {
  description = "(optional) - Whether the screenboard is shared or not"
  type        = bool
  default     = null
}

variable "title" {
  description = "(required) - Name of the screenboard"
  type        = string
}

variable "width" {
  description = "(optional) - Width of the screenboard"
  type        = string
  default     = null
}

variable "template_variable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
      name    = string
      prefix  = string
    }
  ))
  default = []
}

variable "widget" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      alert_id                  = number
      auto_refresh              = bool
      bgcolor                   = string
      check                     = string
      color                     = string
      color_preference          = string
      columns                   = string
      display_format            = string
      env                       = string
      event_size                = string
      font_size                 = string
      group                     = string
      group_by                  = list(string)
      grouping                  = string
      height                    = number
      hide_zero_counts          = bool
      html                      = string
      layout_version            = string
      legend                    = bool
      legend_size               = string
      logset                    = string
      manage_status_show_title  = bool
      manage_status_title_align = string
      manage_status_title_size  = string
      manage_status_title_text  = string
      margin                    = string
      monitor                   = map(string)
      must_show_breakdown       = bool
      must_show_distribution    = bool
      must_show_errors          = bool
      must_show_hits            = bool
      must_show_latency         = bool
      must_show_resource_list   = bool
      params                    = map(string)
      precision                 = string
      query                     = string
      rule = list(object(
        {
          color     = string
          threshold = number
          timeframe = string
        }
      ))
      service_name        = string
      service_service     = string
      show_last_triggered = bool
      size_version        = string
      sizing              = string
      summary_type        = string
      tags                = list(string)
      text                = string
      text_align          = string
      text_size           = string
      tick                = bool
      tick_edge           = string
      tick_pos            = string
      tile_def = list(object(
        {
          autoscale   = bool
          custom_unit = string
          event = list(object(
            {
              q = string
            }
          ))
          group = list(string)
          marker = list(object(
            {
              label = string
              type  = string
              value = string
            }
          ))
          no_group_hosts  = bool
          no_metric_hosts = bool
          node_type       = string
          precision       = string
          request = list(object(
            {
              aggregator = string
              apm_query = list(object(
                {
                  compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = string
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  search = list(object(
                    {
                      query = string
                    }
                  ))
                }
              ))
              change_type = string
              compare_to  = string
              conditional_format = list(object(
                {
                  color           = string
                  comparator      = string
                  custom_bg_color = string
                  invert          = bool
                  palette         = string
                  value           = string
                }
              ))
              extra_col     = string
              increase_good = bool
              limit         = number
              log_query = list(object(
                {
                  compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = string
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  search = list(object(
                    {
                      query = string
                    }
                  ))
                }
              ))
              metadata_json = string
              metric        = string
              order_by      = string
              order_dir     = string
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q           = string
              query_type  = string
              style       = map(string)
              tag_filters = list(string)
              text_filter = string
              type        = string
            }
          ))
          scope      = list(string)
          style      = map(string)
          text_align = string
          viz        = string
        }
      ))
      time        = map(string)
      timeframes  = list(string)
      title       = string
      title_align = string
      title_size  = number
      type        = string
      unit        = string
      url         = string
      viz_type    = string
      width       = number
      x           = number
      y           = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "datadog_screenboard" "this" {
  height    = var.height
  read_only = var.read_only
  shared    = var.shared
  title     = var.title
  width     = var.width

  dynamic "template_variable" {
    for_each = var.template_variable
    content {
      default = template_variable.value["default"]
      name    = template_variable.value["name"]
      prefix  = template_variable.value["prefix"]
    }
  }

  dynamic "widget" {
    for_each = var.widget
    content {
      alert_id                  = widget.value["alert_id"]
      auto_refresh              = widget.value["auto_refresh"]
      bgcolor                   = widget.value["bgcolor"]
      check                     = widget.value["check"]
      color                     = widget.value["color"]
      color_preference          = widget.value["color_preference"]
      columns                   = widget.value["columns"]
      display_format            = widget.value["display_format"]
      env                       = widget.value["env"]
      event_size                = widget.value["event_size"]
      font_size                 = widget.value["font_size"]
      group                     = widget.value["group"]
      group_by                  = widget.value["group_by"]
      grouping                  = widget.value["grouping"]
      height                    = widget.value["height"]
      hide_zero_counts          = widget.value["hide_zero_counts"]
      html                      = widget.value["html"]
      layout_version            = widget.value["layout_version"]
      legend                    = widget.value["legend"]
      legend_size               = widget.value["legend_size"]
      logset                    = widget.value["logset"]
      manage_status_show_title  = widget.value["manage_status_show_title"]
      manage_status_title_align = widget.value["manage_status_title_align"]
      manage_status_title_size  = widget.value["manage_status_title_size"]
      manage_status_title_text  = widget.value["manage_status_title_text"]
      margin                    = widget.value["margin"]
      monitor                   = widget.value["monitor"]
      must_show_breakdown       = widget.value["must_show_breakdown"]
      must_show_distribution    = widget.value["must_show_distribution"]
      must_show_errors          = widget.value["must_show_errors"]
      must_show_hits            = widget.value["must_show_hits"]
      must_show_latency         = widget.value["must_show_latency"]
      must_show_resource_list   = widget.value["must_show_resource_list"]
      params                    = widget.value["params"]
      precision                 = widget.value["precision"]
      query                     = widget.value["query"]
      service_name              = widget.value["service_name"]
      service_service           = widget.value["service_service"]
      show_last_triggered       = widget.value["show_last_triggered"]
      size_version              = widget.value["size_version"]
      sizing                    = widget.value["sizing"]
      summary_type              = widget.value["summary_type"]
      tags                      = widget.value["tags"]
      text                      = widget.value["text"]
      text_align                = widget.value["text_align"]
      text_size                 = widget.value["text_size"]
      tick                      = widget.value["tick"]
      tick_edge                 = widget.value["tick_edge"]
      tick_pos                  = widget.value["tick_pos"]
      time                      = widget.value["time"]
      timeframes                = widget.value["timeframes"]
      title                     = widget.value["title"]
      title_align               = widget.value["title_align"]
      title_size                = widget.value["title_size"]
      type                      = widget.value["type"]
      unit                      = widget.value["unit"]
      url                       = widget.value["url"]
      viz_type                  = widget.value["viz_type"]
      width                     = widget.value["width"]
      x                         = widget.value["x"]
      y                         = widget.value["y"]

      dynamic "rule" {
        for_each = widget.value.rule
        content {
          color     = rule.value["color"]
          threshold = rule.value["threshold"]
          timeframe = rule.value["timeframe"]
        }
      }

      dynamic "tile_def" {
        for_each = widget.value.tile_def
        content {
          autoscale       = tile_def.value["autoscale"]
          custom_unit     = tile_def.value["custom_unit"]
          group           = tile_def.value["group"]
          no_group_hosts  = tile_def.value["no_group_hosts"]
          no_metric_hosts = tile_def.value["no_metric_hosts"]
          node_type       = tile_def.value["node_type"]
          precision       = tile_def.value["precision"]
          scope           = tile_def.value["scope"]
          style           = tile_def.value["style"]
          text_align      = tile_def.value["text_align"]
          viz             = tile_def.value["viz"]

          dynamic "event" {
            for_each = tile_def.value.event
            content {
              q = event.value["q"]
            }
          }

          dynamic "marker" {
            for_each = tile_def.value.marker
            content {
              label = marker.value["label"]
              type  = marker.value["type"]
              value = marker.value["value"]
            }
          }

          dynamic "request" {
            for_each = tile_def.value.request
            content {
              aggregator    = request.value["aggregator"]
              change_type   = request.value["change_type"]
              compare_to    = request.value["compare_to"]
              extra_col     = request.value["extra_col"]
              increase_good = request.value["increase_good"]
              limit         = request.value["limit"]
              metadata_json = request.value["metadata_json"]
              metric        = request.value["metric"]
              order_by      = request.value["order_by"]
              order_dir     = request.value["order_dir"]
              q             = request.value["q"]
              query_type    = request.value["query_type"]
              style         = request.value["style"]
              tag_filters   = request.value["tag_filters"]
              text_filter   = request.value["text_filter"]
              type          = request.value["type"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  index = apm_query.value["index"]

                  dynamic "compute" {
                    for_each = apm_query.value.compute
                    content {
                      aggregation = compute.value["aggregation"]
                      facet       = compute.value["facet"]
                      interval    = compute.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      facet = group_by.value["facet"]
                      limit = group_by.value["limit"]

                      dynamic "sort" {
                        for_each = group_by.value.sort
                        content {
                          aggregation = sort.value["aggregation"]
                          facet       = sort.value["facet"]
                          order       = sort.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "search" {
                    for_each = apm_query.value.search
                    content {
                      query = search.value["query"]
                    }
                  }

                }
              }

              dynamic "conditional_format" {
                for_each = request.value.conditional_format
                content {
                  color           = conditional_format.value["color"]
                  comparator      = conditional_format.value["comparator"]
                  custom_bg_color = conditional_format.value["custom_bg_color"]
                  invert          = conditional_format.value["invert"]
                  palette         = conditional_format.value["palette"]
                  value           = conditional_format.value["value"]
                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  index = log_query.value["index"]

                  dynamic "compute" {
                    for_each = log_query.value.compute
                    content {
                      aggregation = compute.value["aggregation"]
                      facet       = compute.value["facet"]
                      interval    = compute.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      facet = group_by.value["facet"]
                      limit = group_by.value["limit"]

                      dynamic "sort" {
                        for_each = group_by.value.sort
                        content {
                          aggregation = sort.value["aggregation"]
                          facet       = sort.value["facet"]
                          order       = sort.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "search" {
                    for_each = log_query.value.search
                    content {
                      query = search.value["query"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  filter_by = process_query.value["filter_by"]
                  limit     = process_query.value["limit"]
                  metric    = process_query.value["metric"]
                  search_by = process_query.value["search_by"]
                }
              }

            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_screenboard.this.id
}

output "this" {
  value = datadog_screenboard.this
}
```

[top](#index)