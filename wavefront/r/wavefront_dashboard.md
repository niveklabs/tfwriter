# wavefront_dashboard

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_dashboard" {
  source = "./modules/wavefront/r/wavefront_dashboard"

  # can_modify - (optional) is a type of set of string
  can_modify = []
  # can_view - (optional) is a type of set of string
  can_view = []
  # description - (required) is a type of string
  description = null
  # display_query_parameters - (optional) is a type of bool
  display_query_parameters = null
  # display_section_table_of_contents - (optional) is a type of bool
  display_section_table_of_contents = null
  # event_filter_type - (optional) is a type of string
  event_filter_type = null
  # name - (required) is a type of string
  name = null
  # tags - (required) is a type of set of string
  tags = []
  # url - (required) is a type of string
  url = null

  parameter_details = [{
    default_value              = null
    dynamic_field_type         = null
    hide_from_view             = null
    label                      = null
    name                       = null
    parameter_type             = null
    query_value                = null
    tag_key                    = null
    values_to_readable_strings = {}
  }]

  section = [{
    name = null
    row = [{
      chart = [{
        base            = null
        chart_attribute = null
        chart_setting = [{
          auto_column_tags                      = null
          column_tags                           = null
          custom_tags                           = []
          expected_data_spacing                 = null
          fixed_legend_display_stats            = []
          fixed_legend_enabled                  = null
          fixed_legend_filter_field             = null
          fixed_legend_filter_limit             = null
          fixed_legend_filter_sort              = null
          fixed_legend_hide_label               = null
          fixed_legend_position                 = null
          fixed_legend_use_raw_stats            = null
          group_by_source                       = null
          invert_dynamic_legend_hover_control   = null
          line_type                             = null
          max                                   = null
          min                                   = null
          num_tags                              = null
          plain_markdown_content                = null
          show_hosts                            = null
          show_labels                           = null
          show_raw_values                       = null
          sort_values_descending                = null
          sparkline_decimal_precision           = null
          sparkline_display_color               = null
          sparkline_display_font_size           = null
          sparkline_display_horizontal_position = null
          sparkline_display_postfix             = null
          sparkline_display_prefix              = null
          sparkline_display_value_type          = null
          sparkline_display_vertical_position   = null
          sparkline_fill_color                  = null
          sparkline_line_color                  = null
          sparkline_size                        = null
          sparkline_value_color_map_apply_to    = null
          sparkline_value_color_map_colors      = []
          sparkline_value_color_map_values      = []
          sparkline_value_color_map_values_v2   = []
          sparkline_value_text_map_text         = []
          sparkline_value_text_map_thresholds   = []
          stack_type                            = null
          tag_mode                              = null
          time_based_coloring                   = null
          type                                  = null
          window_size                           = null
          windowing                             = null
          xmax                                  = null
          xmin                                  = null
          y0_scale_si_by_1024                   = null
          y0_unit_autoscaling                   = null
          y1_scale_si_by_1024                   = null
          y1_unit_autoscaling                   = null
          y1_units                              = null
          y1max                                 = null
          y1min                                 = null
          ymax                                  = null
          ymin                                  = null
        }]
        description = null
        name        = null
        source = [{
          disabled              = null
          name                  = null
          query                 = null
          query_builder_enabled = null
          scatter_plot_source   = null
          source_description    = null
        }]
        summarization = null
        units         = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "can_modify" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "can_view" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "display_query_parameters" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "display_section_table_of_contents" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "event_filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(required)"
  type        = set(string)
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "parameter_details" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_value              = string
      dynamic_field_type         = string
      hide_from_view             = bool
      label                      = string
      name                       = string
      parameter_type             = string
      query_value                = string
      tag_key                    = string
      values_to_readable_strings = map(string)
    }
  ))
  default = []
}

variable "section" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
      row = list(object(
        {
          chart = list(object(
            {
              base            = number
              chart_attribute = string
              chart_setting = list(object(
                {
                  auto_column_tags                      = bool
                  column_tags                           = string
                  custom_tags                           = list(string)
                  expected_data_spacing                 = number
                  fixed_legend_display_stats            = list(string)
                  fixed_legend_enabled                  = bool
                  fixed_legend_filter_field             = string
                  fixed_legend_filter_limit             = number
                  fixed_legend_filter_sort              = string
                  fixed_legend_hide_label               = bool
                  fixed_legend_position                 = string
                  fixed_legend_use_raw_stats            = bool
                  group_by_source                       = bool
                  invert_dynamic_legend_hover_control   = bool
                  line_type                             = string
                  max                                   = number
                  min                                   = number
                  num_tags                              = number
                  plain_markdown_content                = string
                  show_hosts                            = bool
                  show_labels                           = bool
                  show_raw_values                       = bool
                  sort_values_descending                = bool
                  sparkline_decimal_precision           = number
                  sparkline_display_color               = string
                  sparkline_display_font_size           = string
                  sparkline_display_horizontal_position = string
                  sparkline_display_postfix             = string
                  sparkline_display_prefix              = string
                  sparkline_display_value_type          = string
                  sparkline_display_vertical_position   = string
                  sparkline_fill_color                  = string
                  sparkline_line_color                  = string
                  sparkline_size                        = string
                  sparkline_value_color_map_apply_to    = string
                  sparkline_value_color_map_colors      = list(string)
                  sparkline_value_color_map_values      = list(number)
                  sparkline_value_color_map_values_v2   = list(number)
                  sparkline_value_text_map_text         = list(string)
                  sparkline_value_text_map_thresholds   = list(number)
                  stack_type                            = string
                  tag_mode                              = string
                  time_based_coloring                   = bool
                  type                                  = string
                  window_size                           = number
                  windowing                             = string
                  xmax                                  = number
                  xmin                                  = number
                  y0_scale_si_by_1024                   = bool
                  y0_unit_autoscaling                   = bool
                  y1_scale_si_by_1024                   = bool
                  y1_unit_autoscaling                   = bool
                  y1_units                              = string
                  y1max                                 = number
                  y1min                                 = number
                  ymax                                  = number
                  ymin                                  = number
                }
              ))
              description = string
              name        = string
              source = list(object(
                {
                  disabled              = bool
                  name                  = string
                  query                 = string
                  query_builder_enabled = bool
                  scatter_plot_source   = string
                  source_description    = string
                }
              ))
              summarization = string
              units         = string
            }
          ))
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_dashboard" "this" {
  # can_modify - (optional) is a type of set of string
  can_modify = var.can_modify
  # can_view - (optional) is a type of set of string
  can_view = var.can_view
  # description - (required) is a type of string
  description = var.description
  # display_query_parameters - (optional) is a type of bool
  display_query_parameters = var.display_query_parameters
  # display_section_table_of_contents - (optional) is a type of bool
  display_section_table_of_contents = var.display_section_table_of_contents
  # event_filter_type - (optional) is a type of string
  event_filter_type = var.event_filter_type
  # name - (required) is a type of string
  name = var.name
  # tags - (required) is a type of set of string
  tags = var.tags
  # url - (required) is a type of string
  url = var.url

  dynamic "parameter_details" {
    for_each = var.parameter_details
    content {
      # default_value - (required) is a type of string
      default_value = parameter_details.value["default_value"]
      # dynamic_field_type - (optional) is a type of string
      dynamic_field_type = parameter_details.value["dynamic_field_type"]
      # hide_from_view - (required) is a type of bool
      hide_from_view = parameter_details.value["hide_from_view"]
      # label - (required) is a type of string
      label = parameter_details.value["label"]
      # name - (required) is a type of string
      name = parameter_details.value["name"]
      # parameter_type - (required) is a type of string
      parameter_type = parameter_details.value["parameter_type"]
      # query_value - (optional) is a type of string
      query_value = parameter_details.value["query_value"]
      # tag_key - (optional) is a type of string
      tag_key = parameter_details.value["tag_key"]
      # values_to_readable_strings - (required) is a type of map of string
      values_to_readable_strings = parameter_details.value["values_to_readable_strings"]
    }
  }

  dynamic "section" {
    for_each = var.section
    content {
      # name - (required) is a type of string
      name = section.value["name"]

      dynamic "row" {
        for_each = section.value.row
        content {

          dynamic "chart" {
            for_each = row.value.chart
            content {
              # base - (optional) is a type of number
              base = chart.value["base"]
              # chart_attribute - (optional) is a type of string
              chart_attribute = chart.value["chart_attribute"]
              # description - (optional) is a type of string
              description = chart.value["description"]
              # name - (required) is a type of string
              name = chart.value["name"]
              # summarization - (required) is a type of string
              summarization = chart.value["summarization"]
              # units - (required) is a type of string
              units = chart.value["units"]

              dynamic "chart_setting" {
                for_each = chart.value.chart_setting
                content {
                  # auto_column_tags - (optional) is a type of bool
                  auto_column_tags = chart_setting.value["auto_column_tags"]
                  # column_tags - (optional) is a type of string
                  column_tags = chart_setting.value["column_tags"]
                  # custom_tags - (optional) is a type of list of string
                  custom_tags = chart_setting.value["custom_tags"]
                  # expected_data_spacing - (optional) is a type of number
                  expected_data_spacing = chart_setting.value["expected_data_spacing"]
                  # fixed_legend_display_stats - (optional) is a type of list of string
                  fixed_legend_display_stats = chart_setting.value["fixed_legend_display_stats"]
                  # fixed_legend_enabled - (optional) is a type of bool
                  fixed_legend_enabled = chart_setting.value["fixed_legend_enabled"]
                  # fixed_legend_filter_field - (optional) is a type of string
                  fixed_legend_filter_field = chart_setting.value["fixed_legend_filter_field"]
                  # fixed_legend_filter_limit - (optional) is a type of number
                  fixed_legend_filter_limit = chart_setting.value["fixed_legend_filter_limit"]
                  # fixed_legend_filter_sort - (optional) is a type of string
                  fixed_legend_filter_sort = chart_setting.value["fixed_legend_filter_sort"]
                  # fixed_legend_hide_label - (optional) is a type of bool
                  fixed_legend_hide_label = chart_setting.value["fixed_legend_hide_label"]
                  # fixed_legend_position - (optional) is a type of string
                  fixed_legend_position = chart_setting.value["fixed_legend_position"]
                  # fixed_legend_use_raw_stats - (optional) is a type of bool
                  fixed_legend_use_raw_stats = chart_setting.value["fixed_legend_use_raw_stats"]
                  # group_by_source - (optional) is a type of bool
                  group_by_source = chart_setting.value["group_by_source"]
                  # invert_dynamic_legend_hover_control - (optional) is a type of bool
                  invert_dynamic_legend_hover_control = chart_setting.value["invert_dynamic_legend_hover_control"]
                  # line_type - (optional) is a type of string
                  line_type = chart_setting.value["line_type"]
                  # max - (optional) is a type of number
                  max = chart_setting.value["max"]
                  # min - (optional) is a type of number
                  min = chart_setting.value["min"]
                  # num_tags - (optional) is a type of number
                  num_tags = chart_setting.value["num_tags"]
                  # plain_markdown_content - (optional) is a type of string
                  plain_markdown_content = chart_setting.value["plain_markdown_content"]
                  # show_hosts - (optional) is a type of bool
                  show_hosts = chart_setting.value["show_hosts"]
                  # show_labels - (optional) is a type of bool
                  show_labels = chart_setting.value["show_labels"]
                  # show_raw_values - (optional) is a type of bool
                  show_raw_values = chart_setting.value["show_raw_values"]
                  # sort_values_descending - (optional) is a type of bool
                  sort_values_descending = chart_setting.value["sort_values_descending"]
                  # sparkline_decimal_precision - (optional) is a type of number
                  sparkline_decimal_precision = chart_setting.value["sparkline_decimal_precision"]
                  # sparkline_display_color - (optional) is a type of string
                  sparkline_display_color = chart_setting.value["sparkline_display_color"]
                  # sparkline_display_font_size - (optional) is a type of string
                  sparkline_display_font_size = chart_setting.value["sparkline_display_font_size"]
                  # sparkline_display_horizontal_position - (optional) is a type of string
                  sparkline_display_horizontal_position = chart_setting.value["sparkline_display_horizontal_position"]
                  # sparkline_display_postfix - (optional) is a type of string
                  sparkline_display_postfix = chart_setting.value["sparkline_display_postfix"]
                  # sparkline_display_prefix - (optional) is a type of string
                  sparkline_display_prefix = chart_setting.value["sparkline_display_prefix"]
                  # sparkline_display_value_type - (optional) is a type of string
                  sparkline_display_value_type = chart_setting.value["sparkline_display_value_type"]
                  # sparkline_display_vertical_position - (optional) is a type of string
                  sparkline_display_vertical_position = chart_setting.value["sparkline_display_vertical_position"]
                  # sparkline_fill_color - (optional) is a type of string
                  sparkline_fill_color = chart_setting.value["sparkline_fill_color"]
                  # sparkline_line_color - (optional) is a type of string
                  sparkline_line_color = chart_setting.value["sparkline_line_color"]
                  # sparkline_size - (optional) is a type of string
                  sparkline_size = chart_setting.value["sparkline_size"]
                  # sparkline_value_color_map_apply_to - (optional) is a type of string
                  sparkline_value_color_map_apply_to = chart_setting.value["sparkline_value_color_map_apply_to"]
                  # sparkline_value_color_map_colors - (optional) is a type of list of string
                  sparkline_value_color_map_colors = chart_setting.value["sparkline_value_color_map_colors"]
                  # sparkline_value_color_map_values - (optional) is a type of list of number
                  sparkline_value_color_map_values = chart_setting.value["sparkline_value_color_map_values"]
                  # sparkline_value_color_map_values_v2 - (optional) is a type of list of number
                  sparkline_value_color_map_values_v2 = chart_setting.value["sparkline_value_color_map_values_v2"]
                  # sparkline_value_text_map_text - (optional) is a type of list of string
                  sparkline_value_text_map_text = chart_setting.value["sparkline_value_text_map_text"]
                  # sparkline_value_text_map_thresholds - (optional) is a type of list of number
                  sparkline_value_text_map_thresholds = chart_setting.value["sparkline_value_text_map_thresholds"]
                  # stack_type - (optional) is a type of string
                  stack_type = chart_setting.value["stack_type"]
                  # tag_mode - (optional) is a type of string
                  tag_mode = chart_setting.value["tag_mode"]
                  # time_based_coloring - (optional) is a type of bool
                  time_based_coloring = chart_setting.value["time_based_coloring"]
                  # type - (required) is a type of string
                  type = chart_setting.value["type"]
                  # window_size - (optional) is a type of number
                  window_size = chart_setting.value["window_size"]
                  # windowing - (optional) is a type of string
                  windowing = chart_setting.value["windowing"]
                  # xmax - (optional) is a type of number
                  xmax = chart_setting.value["xmax"]
                  # xmin - (optional) is a type of number
                  xmin = chart_setting.value["xmin"]
                  # y0_scale_si_by_1024 - (optional) is a type of bool
                  y0_scale_si_by_1024 = chart_setting.value["y0_scale_si_by_1024"]
                  # y0_unit_autoscaling - (optional) is a type of bool
                  y0_unit_autoscaling = chart_setting.value["y0_unit_autoscaling"]
                  # y1_scale_si_by_1024 - (optional) is a type of bool
                  y1_scale_si_by_1024 = chart_setting.value["y1_scale_si_by_1024"]
                  # y1_unit_autoscaling - (optional) is a type of bool
                  y1_unit_autoscaling = chart_setting.value["y1_unit_autoscaling"]
                  # y1_units - (optional) is a type of string
                  y1_units = chart_setting.value["y1_units"]
                  # y1max - (optional) is a type of number
                  y1max = chart_setting.value["y1max"]
                  # y1min - (optional) is a type of number
                  y1min = chart_setting.value["y1min"]
                  # ymax - (optional) is a type of number
                  ymax = chart_setting.value["ymax"]
                  # ymin - (optional) is a type of number
                  ymin = chart_setting.value["ymin"]
                }
              }

              dynamic "source" {
                for_each = chart.value.source
                content {
                  # disabled - (optional) is a type of bool
                  disabled = source.value["disabled"]
                  # name - (required) is a type of string
                  name = source.value["name"]
                  # query - (required) is a type of string
                  query = source.value["query"]
                  # query_builder_enabled - (optional) is a type of bool
                  query_builder_enabled = source.value["query_builder_enabled"]
                  # scatter_plot_source - (optional) is a type of string
                  scatter_plot_source = source.value["scatter_plot_source"]
                  # source_description - (optional) is a type of string
                  source_description = source.value["source_description"]
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
output "can_modify" {
  description = "returns a set of string"
  value       = wavefront_dashboard.this.can_modify
}

output "id" {
  description = "returns a string"
  value       = wavefront_dashboard.this.id
}

output "this" {
  value = wavefront_dashboard.this
}
```

[top](#index)