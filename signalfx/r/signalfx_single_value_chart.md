# signalfx_single_value_chart

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
module "signalfx_single_value_chart" {
  source = "./modules/signalfx/r/signalfx_single_value_chart"

  # color_by - (optional) is a type of string
  color_by = null
  # description - (optional) is a type of string
  description = null
  # is_timestamp_hidden - (optional) is a type of bool
  is_timestamp_hidden = null
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
  # show_spark_line - (optional) is a type of bool
  show_spark_line = null
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
  description = "(optional) - (Metric by default) Must be \"Metric\", \"Dimension\", or \"Scale\". \"Scale\" maps to Color by Value in the UI"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the chart (Optional)"
  type        = string
  default     = null
}

variable "is_timestamp_hidden" {
  description = "(optional) - (false by default) Whether to hide the timestamp in the chart"
  type        = bool
  default     = null
}

variable "max_delay" {
  description = "(optional) - How long (in seconds) to wait for late datapoints"
  type        = number
  default     = null
}

variable "max_precision" {
  description = "(optional) - The maximum precision to for values displayed in the list"
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

variable "show_spark_line" {
  description = "(optional) - (false by default) Whether to show a trend line below the current value"
  type        = bool
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
resource "signalfx_single_value_chart" "this" {
  color_by                = var.color_by
  description             = var.description
  is_timestamp_hidden     = var.is_timestamp_hidden
  max_delay               = var.max_delay
  max_precision           = var.max_precision
  name                    = var.name
  program_text            = var.program_text
  refresh_interval        = var.refresh_interval
  secondary_visualization = var.secondary_visualization
  show_spark_line         = var.show_spark_line
  timezone                = var.timezone
  unit_prefix             = var.unit_prefix

  dynamic "color_scale" {
    for_each = var.color_scale
    content {
      color = color_scale.value["color"]
      gt    = color_scale.value["gt"]
      gte   = color_scale.value["gte"]
      lt    = color_scale.value["lt"]
      lte   = color_scale.value["lte"]
    }
  }

  dynamic "viz_options" {
    for_each = var.viz_options
    content {
      color        = viz_options.value["color"]
      display_name = viz_options.value["display_name"]
      label        = viz_options.value["label"]
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
  value       = signalfx_single_value_chart.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_single_value_chart.this.url
}

output "this" {
  value = signalfx_single_value_chart.this
}
```

[top](#index)