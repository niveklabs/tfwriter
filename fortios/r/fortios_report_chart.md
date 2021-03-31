# fortios_report_chart

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_report_chart" {
  source = "./modules/fortios/r/fortios_report_chart"

  # background - (optional) is a type of string
  background = null
  # category - (optional) is a type of string
  category = null
  # color_palette - (optional) is a type of string
  color_palette = null
  # comments - (required) is a type of string
  comments = null
  # dataset - (required) is a type of string
  dataset = null
  # dimension - (optional) is a type of string
  dimension = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # favorite - (optional) is a type of string
  favorite = null
  # graph_type - (optional) is a type of string
  graph_type = null
  # legend - (optional) is a type of string
  legend = null
  # legend_font_size - (optional) is a type of number
  legend_font_size = null
  # name - (required) is a type of string
  name = null
  # period - (optional) is a type of string
  period = null
  # policy - (optional) is a type of number
  policy = null
  # style - (optional) is a type of string
  style = null
  # title - (optional) is a type of string
  title = null
  # title_font_size - (optional) is a type of number
  title_font_size = null
  # type - (optional) is a type of string
  type = null

  category_series = [{
    databind  = null
    font_size = null
  }]

  column = [{
    detail_unit  = null
    detail_value = null
    footer_unit  = null
    footer_value = null
    header_value = null
    id           = null
    mapping = [{
      displayname = null
      id          = null
      op          = null
      value1      = null
      value2      = null
      value_type  = null
    }]
  }]

  drill_down_charts = [{
    chart_name = null
    id         = null
    status     = null
  }]

  value_series = [{
    databind = null
  }]

  x_series = [{
    caption           = null
    caption_font_size = null
    databind          = null
    font_size         = null
    is_category       = null
    label_angle       = null
    scale_direction   = null
    scale_format      = null
    scale_step        = null
    scale_unit        = null
    unit              = null
  }]

  y_series = [{
    caption           = null
    caption_font_size = null
    databind          = null
    extra_databind    = null
    extra_y           = null
    extra_y_legend    = null
    font_size         = null
    group             = null
    label_angle       = null
    unit              = null
    y_legend          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "background" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color_palette" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(required)"
  type        = string
}

variable "dataset" {
  description = "(required)"
  type        = string
}

variable "dimension" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "favorite" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graph_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "legend" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "legend_font_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title_font_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category_series" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      databind  = string
      font_size = number
    }
  ))
  default = []
}

variable "column" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      detail_unit  = string
      detail_value = string
      footer_unit  = string
      footer_value = string
      header_value = string
      id           = number
      mapping = list(object(
        {
          displayname = string
          id          = number
          op          = string
          value1      = string
          value2      = string
          value_type  = string
        }
      ))
    }
  ))
  default = []
}

variable "drill_down_charts" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      chart_name = string
      id         = number
      status     = string
    }
  ))
  default = []
}

variable "value_series" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      databind = string
    }
  ))
  default = []
}

variable "x_series" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      caption           = string
      caption_font_size = number
      databind          = string
      font_size         = number
      is_category       = string
      label_angle       = string
      scale_direction   = string
      scale_format      = string
      scale_step        = number
      scale_unit        = string
      unit              = string
    }
  ))
  default = []
}

variable "y_series" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      caption           = string
      caption_font_size = number
      databind          = string
      extra_databind    = string
      extra_y           = string
      extra_y_legend    = string
      font_size         = number
      group             = string
      label_angle       = string
      unit              = string
      y_legend          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_report_chart" "this" {
  background            = var.background
  category              = var.category
  color_palette         = var.color_palette
  comments              = var.comments
  dataset               = var.dataset
  dimension             = var.dimension
  dynamic_sort_subtable = var.dynamic_sort_subtable
  favorite              = var.favorite
  graph_type            = var.graph_type
  legend                = var.legend
  legend_font_size      = var.legend_font_size
  name                  = var.name
  period                = var.period
  policy                = var.policy
  style                 = var.style
  title                 = var.title
  title_font_size       = var.title_font_size
  type                  = var.type

  dynamic "category_series" {
    for_each = var.category_series
    content {
      databind  = category_series.value["databind"]
      font_size = category_series.value["font_size"]
    }
  }

  dynamic "column" {
    for_each = var.column
    content {
      detail_unit  = column.value["detail_unit"]
      detail_value = column.value["detail_value"]
      footer_unit  = column.value["footer_unit"]
      footer_value = column.value["footer_value"]
      header_value = column.value["header_value"]
      id           = column.value["id"]

      dynamic "mapping" {
        for_each = column.value.mapping
        content {
          displayname = mapping.value["displayname"]
          id          = mapping.value["id"]
          op          = mapping.value["op"]
          value1      = mapping.value["value1"]
          value2      = mapping.value["value2"]
          value_type  = mapping.value["value_type"]
        }
      }

    }
  }

  dynamic "drill_down_charts" {
    for_each = var.drill_down_charts
    content {
      chart_name = drill_down_charts.value["chart_name"]
      id         = drill_down_charts.value["id"]
      status     = drill_down_charts.value["status"]
    }
  }

  dynamic "value_series" {
    for_each = var.value_series
    content {
      databind = value_series.value["databind"]
    }
  }

  dynamic "x_series" {
    for_each = var.x_series
    content {
      caption           = x_series.value["caption"]
      caption_font_size = x_series.value["caption_font_size"]
      databind          = x_series.value["databind"]
      font_size         = x_series.value["font_size"]
      is_category       = x_series.value["is_category"]
      label_angle       = x_series.value["label_angle"]
      scale_direction   = x_series.value["scale_direction"]
      scale_format      = x_series.value["scale_format"]
      scale_step        = x_series.value["scale_step"]
      scale_unit        = x_series.value["scale_unit"]
      unit              = x_series.value["unit"]
    }
  }

  dynamic "y_series" {
    for_each = var.y_series
    content {
      caption           = y_series.value["caption"]
      caption_font_size = y_series.value["caption_font_size"]
      databind          = y_series.value["databind"]
      extra_databind    = y_series.value["extra_databind"]
      extra_y           = y_series.value["extra_y"]
      extra_y_legend    = y_series.value["extra_y_legend"]
      font_size         = y_series.value["font_size"]
      group             = y_series.value["group"]
      label_angle       = y_series.value["label_angle"]
      unit              = y_series.value["unit"]
      y_legend          = y_series.value["y_legend"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "background" {
  description = "returns a string"
  value       = fortios_report_chart.this.background
}

output "category" {
  description = "returns a string"
  value       = fortios_report_chart.this.category
}

output "color_palette" {
  description = "returns a string"
  value       = fortios_report_chart.this.color_palette
}

output "dimension" {
  description = "returns a string"
  value       = fortios_report_chart.this.dimension
}

output "favorite" {
  description = "returns a string"
  value       = fortios_report_chart.this.favorite
}

output "graph_type" {
  description = "returns a string"
  value       = fortios_report_chart.this.graph_type
}

output "id" {
  description = "returns a string"
  value       = fortios_report_chart.this.id
}

output "legend" {
  description = "returns a string"
  value       = fortios_report_chart.this.legend
}

output "legend_font_size" {
  description = "returns a number"
  value       = fortios_report_chart.this.legend_font_size
}

output "period" {
  description = "returns a string"
  value       = fortios_report_chart.this.period
}

output "policy" {
  description = "returns a number"
  value       = fortios_report_chart.this.policy
}

output "style" {
  description = "returns a string"
  value       = fortios_report_chart.this.style
}

output "title" {
  description = "returns a string"
  value       = fortios_report_chart.this.title
}

output "title_font_size" {
  description = "returns a number"
  value       = fortios_report_chart.this.title_font_size
}

output "type" {
  description = "returns a string"
  value       = fortios_report_chart.this.type
}

output "this" {
  value = fortios_report_chart.this
}
```

[top](#index)