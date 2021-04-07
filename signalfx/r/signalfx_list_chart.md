# signalfx_list_chart

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
module "signalfx_list_chart" {
  source = "./modules/signalfx/r/signalfx_list_chart"

  # color_by - (optional) is a type of string
  color_by = null
  # description - (optional) is a type of string
  description = null
  # disable_sampling - (optional) is a type of bool
  disable_sampling = null
  # end_time - (optional) is a type of number
  end_time = null
  # hide_missing_values - (optional) is a type of bool
  hide_missing_values = null
  # legend_fields_to_hide - (optional) is a type of set of string
  legend_fields_to_hide = []
  # max_delay - (optional) is a type of number
  max_delay = null
  # max_precision - (optional) is a type of number
  max_precision = null
  # name - (required) is a type of string
  name = null
  # program_text - (required) is a type of string
  program_text = null
  # refresh_interval - (optional) is a type of number
  refresh_interval = null
  # secondary_visualization - (optional) is a type of string
  secondary_visualization = null
  # sort_by - (optional) is a type of string
  sort_by = null
  # start_time - (optional) is a type of number
  start_time = null
  # time_range - (optional) is a type of number
  time_range = null
  # timezone - (optional) is a type of string
  timezone = null
  # unit_prefix - (optional) is a type of string
  unit_prefix = null

  color_scale = [{
    color = null
    gt    = null
    gte   = null
    lt    = null
    lte   = null
  }]

  legend_options_fields = [{
    enabled  = null
    property = null
  }]

  viz_options = [{
    color        = null
    display_name = null
    label        = null
    value_prefix = null
    value_suffix = null
    value_unit   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "color_by" {
  description = "(optional) - (Metric by default) Must be \"Scale\", \"Metric\" or \"Dimension\""
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the chart (Optional)"
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

variable "hide_missing_values" {
  description = "(optional) - (false by default) If `true`, missing data points in the chart would be hidden"
  type        = bool
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

variable "max_precision" {
  description = "(optional) - Maximum number of digits to display when rounding values up or down"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the chart"
  type        = string
}

variable "program_text" {
  description = "(required) - Signalflow program text for the chart. More info at \"https://developers.signalfx.com/docs/signalflow-overview\""
  type        = string
}

variable "refresh_interval" {
  description = "(optional) - How often (in seconds) to refresh the values of the list"
  type        = number
  default     = null
}

variable "secondary_visualization" {
  description = "(optional) - (false by default) What kind of secondary visualization to show (None, Radial, Linear, Sparkline)"
  type        = string
  default     = null
}

variable "sort_by" {
  description = "(optional) - The property to use when sorting the elements. Use 'value' if you want to sort by value. Must be prepended with + for ascending or - for descending (e.g. -foo)"
  type        = string
  default     = null
}

variable "start_time" {
  description = "(optional) - Seconds since epoch to start the visualization"
  type        = number
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

variable "color_scale" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      color = string
      gt    = number
      gte   = number
      lt    = number
      lte   = number
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
      color        = string
      display_name = string
      label        = string
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
resource "signalfx_list_chart" "this" {
  # color_by - (optional) is a type of string
  color_by = var.color_by
  # description - (optional) is a type of string
  description = var.description
  # disable_sampling - (optional) is a type of bool
  disable_sampling = var.disable_sampling
  # end_time - (optional) is a type of number
  end_time = var.end_time
  # hide_missing_values - (optional) is a type of bool
  hide_missing_values = var.hide_missing_values
  # legend_fields_to_hide - (optional) is a type of set of string
  legend_fields_to_hide = var.legend_fields_to_hide
  # max_delay - (optional) is a type of number
  max_delay = var.max_delay
  # max_precision - (optional) is a type of number
  max_precision = var.max_precision
  # name - (required) is a type of string
  name = var.name
  # program_text - (required) is a type of string
  program_text = var.program_text
  # refresh_interval - (optional) is a type of number
  refresh_interval = var.refresh_interval
  # secondary_visualization - (optional) is a type of string
  secondary_visualization = var.secondary_visualization
  # sort_by - (optional) is a type of string
  sort_by = var.sort_by
  # start_time - (optional) is a type of number
  start_time = var.start_time
  # time_range - (optional) is a type of number
  time_range = var.time_range
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # unit_prefix - (optional) is a type of string
  unit_prefix = var.unit_prefix

  dynamic "color_scale" {
    for_each = var.color_scale
    content {
      # color - (required) is a type of string
      color = color_scale.value["color"]
      # gt - (optional) is a type of number
      gt = color_scale.value["gt"]
      # gte - (optional) is a type of number
      gte = color_scale.value["gte"]
      # lt - (optional) is a type of number
      lt = color_scale.value["lt"]
      # lte - (optional) is a type of number
      lte = color_scale.value["lte"]
    }
  }

  dynamic "legend_options_fields" {
    for_each = var.legend_options_fields
    content {
      # enabled - (optional) is a type of bool
      enabled = legend_options_fields.value["enabled"]
      # property - (required) is a type of string
      property = legend_options_fields.value["property"]
    }
  }

  dynamic "viz_options" {
    for_each = var.viz_options
    content {
      # color - (optional) is a type of string
      color = viz_options.value["color"]
      # display_name - (optional) is a type of string
      display_name = viz_options.value["display_name"]
      # label - (required) is a type of string
      label = viz_options.value["label"]
      # value_prefix - (optional) is a type of string
      value_prefix = viz_options.value["value_prefix"]
      # value_suffix - (optional) is a type of string
      value_suffix = viz_options.value["value_suffix"]
      # value_unit - (optional) is a type of string
      value_unit = viz_options.value["value_unit"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_list_chart.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_list_chart.this.url
}

output "this" {
  value = signalfx_list_chart.this
}
```

[top](#index)