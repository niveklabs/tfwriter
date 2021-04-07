# signalfx_event_feed_chart

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
module "signalfx_event_feed_chart" {
  source = "./modules/signalfx/r/signalfx_event_feed_chart"

  # description - (optional) is a type of string
  description = null
  # end_time - (optional) is a type of number
  end_time = null
  # name - (required) is a type of string
  name = null
  # program_text - (required) is a type of string
  program_text = null
  # start_time - (optional) is a type of number
  start_time = null
  # time_range - (optional) is a type of number
  time_range = null
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

variable "end_time" {
  description = "(optional) - Seconds since epoch to end the visualization"
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
```

[top](#index)

### Resource

```terraform
resource "signalfx_event_feed_chart" "this" {
  # description - (optional) is a type of string
  description = var.description
  # end_time - (optional) is a type of number
  end_time = var.end_time
  # name - (required) is a type of string
  name = var.name
  # program_text - (required) is a type of string
  program_text = var.program_text
  # start_time - (optional) is a type of number
  start_time = var.start_time
  # time_range - (optional) is a type of number
  time_range = var.time_range
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_event_feed_chart.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_event_feed_chart.this.url
}

output "this" {
  value = signalfx_event_feed_chart.this
}
```

[top](#index)