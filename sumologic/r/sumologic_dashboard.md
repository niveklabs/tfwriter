# sumologic_dashboard

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_dashboard" {
  source = "./modules/sumologic/r/sumologic_dashboard"

  # description - (optional) is a type of string
  description = null
  # folder_id - (optional) is a type of string
  folder_id = null
  # refresh_interval - (optional) is a type of number
  refresh_interval = null
  # theme - (optional) is a type of string
  theme = null
  # title - (required) is a type of string
  title = null

  coloring_rule = [{
    color_threshold = [{
      color = null
      max   = null
      min   = null
    }]
    multiple_series_aggregate_function = null
    scope                              = null
    single_series_aggregate_function   = null
  }]

  layout = [{
    grid = [{
      layout_structure = [{
        key       = null
        structure = null
      }]
    }]
  }]

  panel = [{
    sumo_search_panel = [{
      coloring_rule = [{
        color_threshold = [{
          color = null
          max   = null
          min   = null
        }]
        multiple_series_aggregate_function = null
        scope                              = null
        single_series_aggregate_function   = null
      }]
      description                                 = null
      id                                          = null
      keep_visual_settings_consistent_with_parent = null
      key                                         = null
      linked_dashboard = [{
        id                 = null
        include_time_range = null
        include_variables  = null
        relative_path      = null
      }]
      query = [{
        metrics_query_data = [{
          aggregation_type = null
          filter = [{
            key      = null
            negation = null
            value    = null
          }]
          group_by = null
          metric   = null
          operator = [{
            operator_name = null
            parameter = [{
              key   = null
              value = null
            }]
          }]
        }]
        metrics_query_mode = null
        query_key          = null
        query_string       = null
        query_type         = null
      }]
      time_range = [{
        begin_bounded_time_range = [{
          from = [{
            epoch_time_range = [{
              epoch_millis = null
            }]
            iso8601_time_range = [{
              iso8601_time = null
            }]
            literal_time_range = [{
              range_name = null
            }]
            relative_time_range = [{
              relative_time = null
            }]
          }]
          to = [{
            epoch_time_range = [{
              epoch_millis = null
            }]
            iso8601_time_range = [{
              iso8601_time = null
            }]
            literal_time_range = [{
              range_name = null
            }]
            relative_time_range = [{
              relative_time = null
            }]
          }]
        }]
        complete_literal_time_range = [{
          range_name = null
        }]
      }]
      title           = null
      visual_settings = null
    }]
    text_panel = [{
      id                                          = null
      keep_visual_settings_consistent_with_parent = null
      key                                         = null
      text                                        = null
      title                                       = null
      visual_settings                             = null
    }]
  }]

  time_range = [{
    begin_bounded_time_range = [{
      from = [{
        epoch_time_range = [{
          epoch_millis = null
        }]
        iso8601_time_range = [{
          iso8601_time = null
        }]
        literal_time_range = [{
          range_name = null
        }]
        relative_time_range = [{
          relative_time = null
        }]
      }]
      to = [{
        epoch_time_range = [{
          epoch_millis = null
        }]
        iso8601_time_range = [{
          iso8601_time = null
        }]
        literal_time_range = [{
          range_name = null
        }]
        relative_time_range = [{
          relative_time = null
        }]
      }]
    }]
    complete_literal_time_range = [{
      range_name = null
    }]
  }]

  topology_label_map = [{
    data = [{
      label  = null
      values = []
    }]
  }]

  variable = [{
    allow_multi_select = null
    default_value      = null
    display_name       = null
    hide_from_ui       = null
    id                 = null
    include_all_option = null
    name               = null
    source_definition = [{
      csv_variable_source_definition = [{
        values = null
      }]
      log_query_variable_source_definition = [{
        field = null
        query = null
      }]
      metadata_variable_source_definition = [{
        filter = null
        key    = null
      }]
    }]
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

variable "folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refresh_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "theme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title" {
  description = "(required)"
  type        = string
}

variable "coloring_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      color_threshold = list(object(
        {
          color = string
          max   = number
          min   = number
        }
      ))
      multiple_series_aggregate_function = string
      scope                              = string
      single_series_aggregate_function   = string
    }
  ))
  default = []
}

variable "layout" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      grid = list(object(
        {
          layout_structure = list(object(
            {
              key       = string
              structure = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "panel" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      sumo_search_panel = list(object(
        {
          coloring_rule = list(object(
            {
              color_threshold = list(object(
                {
                  color = string
                  max   = number
                  min   = number
                }
              ))
              multiple_series_aggregate_function = string
              scope                              = string
              single_series_aggregate_function   = string
            }
          ))
          description                                 = string
          id                                          = string
          keep_visual_settings_consistent_with_parent = bool
          key                                         = string
          linked_dashboard = list(object(
            {
              id                 = string
              include_time_range = bool
              include_variables  = bool
              relative_path      = string
            }
          ))
          query = list(object(
            {
              metrics_query_data = list(object(
                {
                  aggregation_type = string
                  filter = list(object(
                    {
                      key      = string
                      negation = bool
                      value    = string
                    }
                  ))
                  group_by = string
                  metric   = string
                  operator = list(object(
                    {
                      operator_name = string
                      parameter = list(object(
                        {
                          key   = string
                          value = string
                        }
                      ))
                    }
                  ))
                }
              ))
              metrics_query_mode = string
              query_key          = string
              query_string       = string
              query_type         = string
            }
          ))
          time_range = list(object(
            {
              begin_bounded_time_range = list(object(
                {
                  from = list(object(
                    {
                      epoch_time_range = list(object(
                        {
                          epoch_millis = number
                        }
                      ))
                      iso8601_time_range = list(object(
                        {
                          iso8601_time = string
                        }
                      ))
                      literal_time_range = list(object(
                        {
                          range_name = string
                        }
                      ))
                      relative_time_range = list(object(
                        {
                          relative_time = string
                        }
                      ))
                    }
                  ))
                  to = list(object(
                    {
                      epoch_time_range = list(object(
                        {
                          epoch_millis = number
                        }
                      ))
                      iso8601_time_range = list(object(
                        {
                          iso8601_time = string
                        }
                      ))
                      literal_time_range = list(object(
                        {
                          range_name = string
                        }
                      ))
                      relative_time_range = list(object(
                        {
                          relative_time = string
                        }
                      ))
                    }
                  ))
                }
              ))
              complete_literal_time_range = list(object(
                {
                  range_name = string
                }
              ))
            }
          ))
          title           = string
          visual_settings = string
        }
      ))
      text_panel = list(object(
        {
          id                                          = string
          keep_visual_settings_consistent_with_parent = bool
          key                                         = string
          text                                        = string
          title                                       = string
          visual_settings                             = string
        }
      ))
    }
  ))
  default = []
}

variable "time_range" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      begin_bounded_time_range = list(object(
        {
          from = list(object(
            {
              epoch_time_range = list(object(
                {
                  epoch_millis = number
                }
              ))
              iso8601_time_range = list(object(
                {
                  iso8601_time = string
                }
              ))
              literal_time_range = list(object(
                {
                  range_name = string
                }
              ))
              relative_time_range = list(object(
                {
                  relative_time = string
                }
              ))
            }
          ))
          to = list(object(
            {
              epoch_time_range = list(object(
                {
                  epoch_millis = number
                }
              ))
              iso8601_time_range = list(object(
                {
                  iso8601_time = string
                }
              ))
              literal_time_range = list(object(
                {
                  range_name = string
                }
              ))
              relative_time_range = list(object(
                {
                  relative_time = string
                }
              ))
            }
          ))
        }
      ))
      complete_literal_time_range = list(object(
        {
          range_name = string
        }
      ))
    }
  ))
}

variable "topology_label_map" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data = list(object(
        {
          label  = string
          values = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "variable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_multi_select = bool
      default_value      = string
      display_name       = string
      hide_from_ui       = bool
      id                 = string
      include_all_option = bool
      name               = string
      source_definition = list(object(
        {
          csv_variable_source_definition = list(object(
            {
              values = string
            }
          ))
          log_query_variable_source_definition = list(object(
            {
              field = string
              query = string
            }
          ))
          metadata_variable_source_definition = list(object(
            {
              filter = string
              key    = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_dashboard" "this" {
  # description - (optional) is a type of string
  description = var.description
  # folder_id - (optional) is a type of string
  folder_id = var.folder_id
  # refresh_interval - (optional) is a type of number
  refresh_interval = var.refresh_interval
  # theme - (optional) is a type of string
  theme = var.theme
  # title - (required) is a type of string
  title = var.title

  dynamic "coloring_rule" {
    for_each = var.coloring_rule
    content {
      # multiple_series_aggregate_function - (required) is a type of string
      multiple_series_aggregate_function = coloring_rule.value["multiple_series_aggregate_function"]
      # scope - (required) is a type of string
      scope = coloring_rule.value["scope"]
      # single_series_aggregate_function - (required) is a type of string
      single_series_aggregate_function = coloring_rule.value["single_series_aggregate_function"]

      dynamic "color_threshold" {
        for_each = coloring_rule.value.color_threshold
        content {
          # color - (required) is a type of string
          color = color_threshold.value["color"]
          # max - (optional) is a type of number
          max = color_threshold.value["max"]
          # min - (optional) is a type of number
          min = color_threshold.value["min"]
        }
      }

    }
  }

  dynamic "layout" {
    for_each = var.layout
    content {

      dynamic "grid" {
        for_each = layout.value.grid
        content {

          dynamic "layout_structure" {
            for_each = grid.value.layout_structure
            content {
              # key - (required) is a type of string
              key = layout_structure.value["key"]
              # structure - (required) is a type of string
              structure = layout_structure.value["structure"]
            }
          }

        }
      }

    }
  }

  dynamic "panel" {
    for_each = var.panel
    content {

      dynamic "sumo_search_panel" {
        for_each = panel.value.sumo_search_panel
        content {
          # description - (optional) is a type of string
          description = sumo_search_panel.value["description"]
          # keep_visual_settings_consistent_with_parent - (optional) is a type of bool
          keep_visual_settings_consistent_with_parent = sumo_search_panel.value["keep_visual_settings_consistent_with_parent"]
          # key - (required) is a type of string
          key = sumo_search_panel.value["key"]
          # title - (optional) is a type of string
          title = sumo_search_panel.value["title"]
          # visual_settings - (optional) is a type of string
          visual_settings = sumo_search_panel.value["visual_settings"]

          dynamic "coloring_rule" {
            for_each = sumo_search_panel.value.coloring_rule
            content {
              # multiple_series_aggregate_function - (required) is a type of string
              multiple_series_aggregate_function = coloring_rule.value["multiple_series_aggregate_function"]
              # scope - (required) is a type of string
              scope = coloring_rule.value["scope"]
              # single_series_aggregate_function - (required) is a type of string
              single_series_aggregate_function = coloring_rule.value["single_series_aggregate_function"]

              dynamic "color_threshold" {
                for_each = coloring_rule.value.color_threshold
                content {
                  # color - (required) is a type of string
                  color = color_threshold.value["color"]
                  # max - (optional) is a type of number
                  max = color_threshold.value["max"]
                  # min - (optional) is a type of number
                  min = color_threshold.value["min"]
                }
              }

            }
          }

          dynamic "linked_dashboard" {
            for_each = sumo_search_panel.value.linked_dashboard
            content {
              # id - (required) is a type of string
              id = linked_dashboard.value["id"]
              # include_time_range - (optional) is a type of bool
              include_time_range = linked_dashboard.value["include_time_range"]
              # include_variables - (optional) is a type of bool
              include_variables = linked_dashboard.value["include_variables"]
              # relative_path - (optional) is a type of string
              relative_path = linked_dashboard.value["relative_path"]
            }
          }

          dynamic "query" {
            for_each = sumo_search_panel.value.query
            content {
              # metrics_query_mode - (optional) is a type of string
              metrics_query_mode = query.value["metrics_query_mode"]
              # query_key - (required) is a type of string
              query_key = query.value["query_key"]
              # query_string - (required) is a type of string
              query_string = query.value["query_string"]
              # query_type - (required) is a type of string
              query_type = query.value["query_type"]

              dynamic "metrics_query_data" {
                for_each = query.value.metrics_query_data
                content {
                  # aggregation_type - (optional) is a type of string
                  aggregation_type = metrics_query_data.value["aggregation_type"]
                  # group_by - (optional) is a type of string
                  group_by = metrics_query_data.value["group_by"]
                  # metric - (required) is a type of string
                  metric = metrics_query_data.value["metric"]

                  dynamic "filter" {
                    for_each = metrics_query_data.value.filter
                    content {
                      # key - (required) is a type of string
                      key = filter.value["key"]
                      # negation - (optional) is a type of bool
                      negation = filter.value["negation"]
                      # value - (required) is a type of string
                      value = filter.value["value"]
                    }
                  }

                  dynamic "operator" {
                    for_each = metrics_query_data.value.operator
                    content {
                      # operator_name - (required) is a type of string
                      operator_name = operator.value["operator_name"]

                      dynamic "parameter" {
                        for_each = operator.value.parameter
                        content {
                          # key - (required) is a type of string
                          key = parameter.value["key"]
                          # value - (required) is a type of string
                          value = parameter.value["value"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "time_range" {
            for_each = sumo_search_panel.value.time_range
            content {

              dynamic "begin_bounded_time_range" {
                for_each = time_range.value.begin_bounded_time_range
                content {

                  dynamic "from" {
                    for_each = begin_bounded_time_range.value.from
                    content {

                      dynamic "epoch_time_range" {
                        for_each = from.value.epoch_time_range
                        content {
                          # epoch_millis - (required) is a type of number
                          epoch_millis = epoch_time_range.value["epoch_millis"]
                        }
                      }

                      dynamic "iso8601_time_range" {
                        for_each = from.value.iso8601_time_range
                        content {
                          # iso8601_time - (required) is a type of string
                          iso8601_time = iso8601_time_range.value["iso8601_time"]
                        }
                      }

                      dynamic "literal_time_range" {
                        for_each = from.value.literal_time_range
                        content {
                          # range_name - (required) is a type of string
                          range_name = literal_time_range.value["range_name"]
                        }
                      }

                      dynamic "relative_time_range" {
                        for_each = from.value.relative_time_range
                        content {
                          # relative_time - (required) is a type of string
                          relative_time = relative_time_range.value["relative_time"]
                        }
                      }

                    }
                  }

                  dynamic "to" {
                    for_each = begin_bounded_time_range.value.to
                    content {

                      dynamic "epoch_time_range" {
                        for_each = to.value.epoch_time_range
                        content {
                          # epoch_millis - (required) is a type of number
                          epoch_millis = epoch_time_range.value["epoch_millis"]
                        }
                      }

                      dynamic "iso8601_time_range" {
                        for_each = to.value.iso8601_time_range
                        content {
                          # iso8601_time - (required) is a type of string
                          iso8601_time = iso8601_time_range.value["iso8601_time"]
                        }
                      }

                      dynamic "literal_time_range" {
                        for_each = to.value.literal_time_range
                        content {
                          # range_name - (required) is a type of string
                          range_name = literal_time_range.value["range_name"]
                        }
                      }

                      dynamic "relative_time_range" {
                        for_each = to.value.relative_time_range
                        content {
                          # relative_time - (required) is a type of string
                          relative_time = relative_time_range.value["relative_time"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "complete_literal_time_range" {
                for_each = time_range.value.complete_literal_time_range
                content {
                  # range_name - (required) is a type of string
                  range_name = complete_literal_time_range.value["range_name"]
                }
              }

            }
          }

        }
      }

      dynamic "text_panel" {
        for_each = panel.value.text_panel
        content {
          # keep_visual_settings_consistent_with_parent - (optional) is a type of bool
          keep_visual_settings_consistent_with_parent = text_panel.value["keep_visual_settings_consistent_with_parent"]
          # key - (required) is a type of string
          key = text_panel.value["key"]
          # text - (optional) is a type of string
          text = text_panel.value["text"]
          # title - (optional) is a type of string
          title = text_panel.value["title"]
          # visual_settings - (optional) is a type of string
          visual_settings = text_panel.value["visual_settings"]
        }
      }

    }
  }

  dynamic "time_range" {
    for_each = var.time_range
    content {

      dynamic "begin_bounded_time_range" {
        for_each = time_range.value.begin_bounded_time_range
        content {

          dynamic "from" {
            for_each = begin_bounded_time_range.value.from
            content {

              dynamic "epoch_time_range" {
                for_each = from.value.epoch_time_range
                content {
                  # epoch_millis - (required) is a type of number
                  epoch_millis = epoch_time_range.value["epoch_millis"]
                }
              }

              dynamic "iso8601_time_range" {
                for_each = from.value.iso8601_time_range
                content {
                  # iso8601_time - (required) is a type of string
                  iso8601_time = iso8601_time_range.value["iso8601_time"]
                }
              }

              dynamic "literal_time_range" {
                for_each = from.value.literal_time_range
                content {
                  # range_name - (required) is a type of string
                  range_name = literal_time_range.value["range_name"]
                }
              }

              dynamic "relative_time_range" {
                for_each = from.value.relative_time_range
                content {
                  # relative_time - (required) is a type of string
                  relative_time = relative_time_range.value["relative_time"]
                }
              }

            }
          }

          dynamic "to" {
            for_each = begin_bounded_time_range.value.to
            content {

              dynamic "epoch_time_range" {
                for_each = to.value.epoch_time_range
                content {
                  # epoch_millis - (required) is a type of number
                  epoch_millis = epoch_time_range.value["epoch_millis"]
                }
              }

              dynamic "iso8601_time_range" {
                for_each = to.value.iso8601_time_range
                content {
                  # iso8601_time - (required) is a type of string
                  iso8601_time = iso8601_time_range.value["iso8601_time"]
                }
              }

              dynamic "literal_time_range" {
                for_each = to.value.literal_time_range
                content {
                  # range_name - (required) is a type of string
                  range_name = literal_time_range.value["range_name"]
                }
              }

              dynamic "relative_time_range" {
                for_each = to.value.relative_time_range
                content {
                  # relative_time - (required) is a type of string
                  relative_time = relative_time_range.value["relative_time"]
                }
              }

            }
          }

        }
      }

      dynamic "complete_literal_time_range" {
        for_each = time_range.value.complete_literal_time_range
        content {
          # range_name - (required) is a type of string
          range_name = complete_literal_time_range.value["range_name"]
        }
      }

    }
  }

  dynamic "topology_label_map" {
    for_each = var.topology_label_map
    content {

      dynamic "data" {
        for_each = topology_label_map.value.data
        content {
          # label - (required) is a type of string
          label = data.value["label"]
          # values - (required) is a type of list of string
          values = data.value["values"]
        }
      }

    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      # allow_multi_select - (optional) is a type of bool
      allow_multi_select = variable.value["allow_multi_select"]
      # default_value - (optional) is a type of string
      default_value = variable.value["default_value"]
      # display_name - (optional) is a type of string
      display_name = variable.value["display_name"]
      # hide_from_ui - (optional) is a type of bool
      hide_from_ui = variable.value["hide_from_ui"]
      # include_all_option - (optional) is a type of bool
      include_all_option = variable.value["include_all_option"]
      # name - (required) is a type of string
      name = variable.value["name"]

      dynamic "source_definition" {
        for_each = variable.value.source_definition
        content {

          dynamic "csv_variable_source_definition" {
            for_each = source_definition.value.csv_variable_source_definition
            content {
              # values - (required) is a type of string
              values = csv_variable_source_definition.value["values"]
            }
          }

          dynamic "log_query_variable_source_definition" {
            for_each = source_definition.value.log_query_variable_source_definition
            content {
              # field - (required) is a type of string
              field = log_query_variable_source_definition.value["field"]
              # query - (required) is a type of string
              query = log_query_variable_source_definition.value["query"]
            }
          }

          dynamic "metadata_variable_source_definition" {
            for_each = source_definition.value.metadata_variable_source_definition
            content {
              # filter - (required) is a type of string
              filter = metadata_variable_source_definition.value["filter"]
              # key - (required) is a type of string
              key = metadata_variable_source_definition.value["key"]
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
  value       = sumologic_dashboard.this.id
}

output "this" {
  value = sumologic_dashboard.this
}
```

[top](#index)