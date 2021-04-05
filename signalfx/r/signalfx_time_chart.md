# signalfx_time_chart

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
module "signalfx_time_chart" {
  source = "./modules/signalfx/r/signalfx_time_chart"

  # axes_include_zero - (optional) is a type of bool
  axes_include_zero = null
  # axes_precision - (optional) is a type of number
  axes_precision = null
  # color_by - (optional) is a type of string
  color_by = null
  # description - (optional) is a type of string
  description = null
  # disable_sampling - (optional) is a type of bool
  disable_sampling = null
  # end_time - (optional) is a type of number
  end_time = null
  # legend_fields_to_hide - (optional) is a type of set of string
  legend_fields_to_hide = []
  # max_delay - (optional) is a type of number
  max_delay = null
  # minimum_resolution - (optional) is a type of number
  minimum_resolution = null
  # name - (required) is a type of string
  name = null
  # on_chart_legend_dimension - (optional) is a type of string
  on_chart_legend_dimension = null
  # plot_type - (optional) is a type of string
  plot_type = null
  # program_text - (required) is a type of string
  program_text = null
  # show_data_markers - (optional) is a type of bool
  show_data_markers = null
  # show_event_lines - (optional) is a type of bool
  show_event_lines = null
  # stacked - (optional) is a type of bool
  stacked = null
  # start_time - (optional) is a type of number
  start_time = null
  # tags - (optional) is a type of list of string
  tags = []
  # time_range - (optional) is a type of number
  time_range = null
  # timezone - (optional) is a type of string
  timezone = null
  # unit_prefix - (optional) is a type of string
  unit_prefix = null

  axis_left = [{
    high_watermark       = null
    high_watermark_label = null
    label                = null
    low_watermark        = null
    low_watermark_label  = null
    max_value            = null
    min_value            = null
    watermarks = [{
      label = null
      value = null
    }]
  }]

  axis_right = [{
    high_watermark       = null
    high_watermark_label = null
    label                = null
    low_watermark        = null
    low_watermark_label  = null
    max_value            = null
    min_value            = null
    watermarks = [{
      label = null
      value = null
    }]
  }]

  event_options = [{
    color        = null
    display_name = null
    label        = null
  }]

  histogram_options = [{
    color_theme = null
  }]

  legend_options_fields = [{
    enabled  = null
    property = null
  }]

  viz_options = [{
    axis         = null
    color        = null
    display_name = null
    label        = null
    plot_type    = null
    value_prefix = null
    value_suffix = null
    value_unit   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "axes_include_zero" {
  description = "(optional) - Force y-axes to always show zero"
  type        = bool
  default     = null
}

variable "axes_precision" {
  description = "(optional) - Force a specific number of significant digits in the y-axis"
  type        = number
  default     = null
}

variable "color_by" {
  description = "(optional) - (Dimension by default) Must be \"Dimension\" or \"Metric\""
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the chart"
  type        = string
  default     = null
}

variable "disable_sampling" {
  description = "(optional) - (false by default) If false, samples a subset of the output MTS, which improves UI performance"
  type        = bool
  default     = null
}

variable "end_time" {
  description = "(optional) - Seconds since epoch to end the visualization"
  type        = number
  default     = null
}

variable "legend_fields_to_hide" {
  description = "(optional) - List of properties that shouldn't be displayed in the chart legend (i.e. dimension names)"
  type        = set(string)
  default     = null
}

variable "max_delay" {
  description = "(optional) - How long (in seconds) to wait for late datapoints"
  type        = number
  default     = null
}

variable "minimum_resolution" {
  description = "(optional) - The minimum resolution (in seconds) to use for computing the underlying program"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the chart"
  type        = string
}

variable "on_chart_legend_dimension" {
  description = "(optional) - Dimension to show in the on-chart legend. On-chart legend is off unless a dimension is specified. Allowed: 'metric', 'plot_label' and any dimension."
  type        = string
  default     = null
}

variable "plot_type" {
  description = "(optional) - (LineChart by default) The default plot display style for the visualization. Must be \"LineChart\", \"AreaChart\", \"ColumnChart\", or \"Histogram\""
  type        = string
  default     = null
}

variable "program_text" {
  description = "(required) - Signalflow program text for the chart. More info at \"https://developers.signalfx.com/docs/signalflow-overview\""
  type        = string
}

variable "show_data_markers" {
  description = "(optional) - (false by default) Show markers (circles) for each datapoint used to draw line or area charts"
  type        = bool
  default     = null
}

variable "show_event_lines" {
  description = "(optional) - (false by default) Whether vertical highlight lines should be drawn in the visualizations at times when events occurred"
  type        = bool
  default     = null
}

variable "stacked" {
  description = "(optional) - (false by default) Whether area and bar charts in the visualization should be stacked"
  type        = bool
  default     = null
}

variable "start_time" {
  description = "(optional) - Seconds since epoch to start the visualization"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Tags associated with the chart"
  type        = list(string)
  default     = null
}

variable "time_range" {
  description = "(optional) - Seconds to display in the visualization. This is a rolling range from the current time. Example: 3600 = `-1h`"
  type        = number
  default     = null
}

variable "timezone" {
  description = "(optional) - The property value is a string that denotes the geographic region associated with the time zone, (e.g. Australia/Sydney)"
  type        = string
  default     = null
}

variable "unit_prefix" {
  description = "(optional) - (Metric by default) Must be \"Metric\" or \"Binary\""
  type        = string
  default     = null
}

variable "axis_left" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      high_watermark       = number
      high_watermark_label = string
      label                = string
      low_watermark        = number
      low_watermark_label  = string
      max_value            = number
      min_value            = number
      watermarks = set(object(
        {
          label = string
          value = number
        }
      ))
    }
  ))
  default = []
}

variable "axis_right" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      high_watermark       = number
      high_watermark_label = string
      label                = string
      low_watermark        = number
      low_watermark_label  = string
      max_value            = number
      min_value            = number
      watermarks = set(object(
        {
          label = string
          value = number
        }
      ))
    }
  ))
  default = []
}

variable "event_options" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      color        = string
      display_name = string
      label        = string
    }
  ))
  default = []
}

variable "histogram_options" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      color_theme = string
    }
  ))
  default = []
}

variable "legend_options_fields" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enabled  = bool
      property = string
    }
  ))
  default = []
}

variable "viz_options" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      axis         = string
      color        = string
      display_name = string
      label        = string
      plot_type    = string
      value_prefix = string
      value_suffix = string
      value_unit   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_time_chart" "this" {
  axes_include_zero         = var.axes_include_zero
  axes_precision            = var.axes_precision
  color_by                  = var.color_by
  description               = var.description
  disable_sampling          = var.disable_sampling
  end_time                  = var.end_time
  legend_fields_to_hide     = var.legend_fields_to_hide
  max_delay                 = var.max_delay
  minimum_resolution        = var.minimum_resolution
  name                      = var.name
  on_chart_legend_dimension = var.on_chart_legend_dimension
  plot_type                 = var.plot_type
  program_text              = var.program_text
  show_data_markers         = var.show_data_markers
  show_event_lines          = var.show_event_lines
  stacked                   = var.stacked
  start_time                = var.start_time
  tags                      = var.tags
  time_range                = var.time_range
  timezone                  = var.timezone
  unit_prefix               = var.unit_prefix

  dynamic "axis_left" {
    for_each = var.axis_left
    content {
      high_watermark       = axis_left.value["high_watermark"]
      high_watermark_label = axis_left.value["high_watermark_label"]
      label                = axis_left.value["label"]
      low_watermark        = axis_left.value["low_watermark"]
      low_watermark_label  = axis_left.value["low_watermark_label"]
      max_value            = axis_left.value["max_value"]
      min_value            = axis_left.value["min_value"]

      dynamic "watermarks" {
        for_each = axis_left.value.watermarks
        content {
          label = watermarks.value["label"]
          value = watermarks.value["value"]
        }
      }

    }
  }

  dynamic "axis_right" {
    for_each = var.axis_right
    content {
      high_watermark       = axis_right.value["high_watermark"]
      high_watermark_label = axis_right.value["high_watermark_label"]
      label                = axis_right.value["label"]
      low_watermark        = axis_right.value["low_watermark"]
      low_watermark_label  = axis_right.value["low_watermark_label"]
      max_value            = axis_right.value["max_value"]
      min_value            = axis_right.value["min_value"]

      dynamic "watermarks" {
        for_each = axis_right.value.watermarks
        content {
          label = watermarks.value["label"]
          value = watermarks.value["value"]
        }
      }

    }
  }

  dynamic "event_options" {
    for_each = var.event_options
    content {
      color        = event_options.value["color"]
      display_name = event_options.value["display_name"]
      label        = event_options.value["label"]
    }
  }

  dynamic "histogram_options" {
    for_each = var.histogram_options
    content {
      color_theme = histogram_options.value["color_theme"]
    }
  }

  dynamic "legend_options_fields" {
    for_each = var.legend_options_fields
    content {
      enabled  = legend_options_fields.value["enabled"]
      property = legend_options_fields.value["property"]
    }
  }

  dynamic "viz_options" {
    for_each = var.viz_options
    content {
      axis         = viz_options.value["axis"]
      color        = viz_options.value["color"]
      display_name = viz_options.value["display_name"]
      label        = viz_options.value["label"]
      plot_type    = viz_options.value["plot_type"]
      value_prefix = viz_options.value["value_prefix"]
      value_suffix = viz_options.value["value_suffix"]
      value_unit   = viz_options.value["value_unit"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_time_chart.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_time_chart.this.url
}

output "this" {
  value = signalfx_time_chart.this
}
```

[top](#index)