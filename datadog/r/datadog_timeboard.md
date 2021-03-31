# datadog_timeboard

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
module "datadog_timeboard" {
  source = "./modules/datadog/r/datadog_timeboard"

  # description - (required) is a type of string
  description = null
  # read_only - (optional) is a type of bool
  read_only = null
  # title - (required) is a type of string
  title = null

  graph = [{
    autoscale               = null
    custom_unit             = null
    events                  = []
    group                   = []
    include_no_metric_hosts = null
    include_ungrouped_hosts = null
    marker = [{
      label = null
      type  = null
      value = null
    }]
    node_type = null
    precision = null
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
        comparator      = null
        custom_bg_color = null
        custom_fg_color = null
        palette         = null
        value           = null
      }]
      extra_col     = null
      increase_good = null
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
      metadata_json   = null
      order_by        = null
      order_direction = null
      process_query = [{
        filter_by = []
        limit     = null
        metric    = null
        search_by = null
      }]
      q       = null
      stacked = null
      style   = {}
      type    = null
    }]
    scope      = []
    style      = {}
    text_align = null
    title      = null
    viz        = null
    yaxis      = {}
  }]

  template_variable = [{
    default = null
    name    = null
    prefix  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - A description of the dashboard's content."
  type        = string
}

variable "read_only" {
  description = "(optional) - The read-only status of the timeboard. Default is false."
  type        = bool
  default     = null
}

variable "title" {
  description = "(required) - The name of the dashboard."
  type        = string
}

variable "graph" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      autoscale               = bool
      custom_unit             = string
      events                  = list(string)
      group                   = list(string)
      include_no_metric_hosts = bool
      include_ungrouped_hosts = bool
      marker = list(object(
        {
          label = string
          type  = string
          value = string
        }
      ))
      node_type = string
      precision = string
      request = list(object(
        {
          aggregator = string
          apm_query = list(object(
            {
              compute = list(object(
                {
                  aggregation = string
                  facet       = string
                  interval    = number
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
              comparator      = string
              custom_bg_color = string
              custom_fg_color = string
              palette         = string
              value           = string
            }
          ))
          extra_col     = string
          increase_good = bool
          log_query = list(object(
            {
              compute = list(object(
                {
                  aggregation = string
                  facet       = string
                  interval    = number
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
          metadata_json   = string
          order_by        = string
          order_direction = string
          process_query = list(object(
            {
              filter_by = list(string)
              limit     = number
              metric    = string
              search_by = string
            }
          ))
          q       = string
          stacked = bool
          style   = map(string)
          type    = string
        }
      ))
      scope      = list(string)
      style      = map(string)
      text_align = string
      title      = string
      viz        = string
      yaxis      = map(string)
    }
  ))
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
```

[top](#index)

### Resource

```terraform
resource "datadog_timeboard" "this" {
  description = var.description
  read_only   = var.read_only
  title       = var.title

  dynamic "graph" {
    for_each = var.graph
    content {
      autoscale               = graph.value["autoscale"]
      custom_unit             = graph.value["custom_unit"]
      events                  = graph.value["events"]
      group                   = graph.value["group"]
      include_no_metric_hosts = graph.value["include_no_metric_hosts"]
      include_ungrouped_hosts = graph.value["include_ungrouped_hosts"]
      node_type               = graph.value["node_type"]
      precision               = graph.value["precision"]
      scope                   = graph.value["scope"]
      style                   = graph.value["style"]
      text_align              = graph.value["text_align"]
      title                   = graph.value["title"]
      viz                     = graph.value["viz"]
      yaxis                   = graph.value["yaxis"]

      dynamic "marker" {
        for_each = graph.value.marker
        content {
          label = marker.value["label"]
          type  = marker.value["type"]
          value = marker.value["value"]
        }
      }

      dynamic "request" {
        for_each = graph.value.request
        content {
          aggregator      = request.value["aggregator"]
          change_type     = request.value["change_type"]
          compare_to      = request.value["compare_to"]
          extra_col       = request.value["extra_col"]
          increase_good   = request.value["increase_good"]
          metadata_json   = request.value["metadata_json"]
          order_by        = request.value["order_by"]
          order_direction = request.value["order_direction"]
          q               = request.value["q"]
          stacked         = request.value["stacked"]
          style           = request.value["style"]
          type            = request.value["type"]

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
              comparator      = conditional_format.value["comparator"]
              custom_bg_color = conditional_format.value["custom_bg_color"]
              custom_fg_color = conditional_format.value["custom_fg_color"]
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

  dynamic "template_variable" {
    for_each = var.template_variable
    content {
      default = template_variable.value["default"]
      name    = template_variable.value["name"]
      prefix  = template_variable.value["prefix"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_timeboard.this.id
}

output "this" {
  value = datadog_timeboard.this
}
```

[top](#index)