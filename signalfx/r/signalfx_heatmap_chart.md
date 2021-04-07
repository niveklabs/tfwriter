# signalfx_heatmap_chart

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
module "signalfx_heatmap_chart" {
  source = "./modules/signalfx/r/signalfx_heatmap_chart"

  # description - (optional) is a type of string
  description = null
  # disable_sampling - (optional) is a type of bool
  disable_sampling = null
  # group_by - (optional) is a type of list of string
  group_by = []
  # hide_timestamp - (optional) is a type of bool
  hide_timestamp = null
  # max_delay - (optional) is a type of number
  max_delay = null
  # minimum_resolution - (optional) is a type of number
  minimum_resolution = null
  # name - (required) is a type of string
  name = null
  # program_text - (required) is a type of string
  program_text = null
  # refresh_interval - (optional) is a type of number
  refresh_interval = null
  # sort_by - (optional) is a type of string
  sort_by = null
  # timezone - (optional) is a type of string
  timezone = null
  # unit_prefix - (optional) is a type of string
  unit_prefix = null

  color_range = [{
    color     = null
    max_value = null
    min_value = null
  }]

  color_scale = [{
    color = null
    gt    = null
    gte   = null
    lt    = null
    lte   = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "group_by" {
  description = "(optional) - Properties to group by in the heatmap (in nesting order)"
  type        = list(string)
  default     = null
}

variable "hide_timestamp" {
  description = "(optional) - (false by default) Whether to show the timestamp in the chart"
  type        = bool
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

variable "program_text" {
  description = "(required) - Signalflow program text for the chart. More info at \"https://developers.signalfx.com/docs/signalflow-overview\""
  type        = string
}

variable "refresh_interval" {
  description = "(optional) - How often (in seconds) to refresh the values of the heatmap"
  type        = number
  default     = null
}

variable "sort_by" {
  description = "(optional) - The property to use when sorting the elements. Must be prepended with + for ascending or - for descending (e.g. -foo)"
  type        = string
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

variable "color_range" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      color     = string
      max_value = number
      min_value = number
    }
  ))
  default = []
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
```

[top](#index)

### Resource

```terraform
resource "signalfx_heatmap_chart" "this" {
  # description - (optional) is a type of string
  description = var.description
  # disable_sampling - (optional) is a type of bool
  disable_sampling = var.disable_sampling
  # group_by - (optional) is a type of list of string
  group_by = var.group_by
  # hide_timestamp - (optional) is a type of bool
  hide_timestamp = var.hide_timestamp
  # max_delay - (optional) is a type of number
  max_delay = var.max_delay
  # minimum_resolution - (optional) is a type of number
  minimum_resolution = var.minimum_resolution
  # name - (required) is a type of string
  name = var.name
  # program_text - (required) is a type of string
  program_text = var.program_text
  # refresh_interval - (optional) is a type of number
  refresh_interval = var.refresh_interval
  # sort_by - (optional) is a type of string
  sort_by = var.sort_by
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # unit_prefix - (optional) is a type of string
  unit_prefix = var.unit_prefix

  dynamic "color_range" {
    for_each = var.color_range
    content {
      # color - (required) is a type of string
      color = color_range.value["color"]
      # max_value - (optional) is a type of number
      max_value = color_range.value["max_value"]
      # min_value - (optional) is a type of number
      min_value = color_range.value["min_value"]
    }
  }

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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_heatmap_chart.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_heatmap_chart.this.url
}

output "this" {
  value = signalfx_heatmap_chart.this
}
```

[top](#index)