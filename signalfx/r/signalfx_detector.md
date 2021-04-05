# signalfx_detector

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
module "signalfx_detector" {
  source = "./modules/signalfx/r/signalfx_detector"

  # authorized_writer_teams - (optional) is a type of set of string
  authorized_writer_teams = []
  # authorized_writer_users - (optional) is a type of set of string
  authorized_writer_users = []
  # description - (optional) is a type of string
  description = null
  # disable_sampling - (optional) is a type of bool
  disable_sampling = null
  # end_time - (optional) is a type of number
  end_time = null
  # max_delay - (optional) is a type of number
  max_delay = null
  # min_delay - (optional) is a type of number
  min_delay = null
  # name - (required) is a type of string
  name = null
  # program_text - (required) is a type of string
  program_text = null
  # show_data_markers - (optional) is a type of bool
  show_data_markers = null
  # show_event_lines - (optional) is a type of bool
  show_event_lines = null
  # start_time - (optional) is a type of number
  start_time = null
  # tags - (optional) is a type of list of string
  tags = []
  # teams - (optional) is a type of list of string
  teams = []
  # time_range - (optional) is a type of number
  time_range = null
  # timezone - (optional) is a type of string
  timezone = null

  rule = [{
    description           = null
    detect_label          = null
    disabled              = null
    notifications         = []
    parameterized_body    = null
    parameterized_subject = null
    runbook_url           = null
    severity              = null
    tip                   = null
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
variable "authorized_writer_teams" {
  description = "(optional) - Team IDs that have write access to this dashboard"
  type        = set(string)
  default     = null
}

variable "authorized_writer_users" {
  description = "(optional) - User IDs that have write access to this dashboard"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of the detector"
  type        = string
  default     = null
}

variable "disable_sampling" {
  description = "(optional) - (false by default) When false, samples a subset of the output MTS in the visualization."
  type        = bool
  default     = null
}

variable "end_time" {
  description = "(optional) - Seconds since epoch. Used for visualization"
  type        = number
  default     = null
}

variable "max_delay" {
  description = "(optional) - Maximum time (in seconds) to wait for late datapoints. Max value is 900 (15m)"
  type        = number
  default     = null
}

variable "min_delay" {
  description = "(optional) - Minimum time (in seconds) for the computation to wait even if the datapoints are arriving in a timely fashion. Max value is 900 (15m)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the detector"
  type        = string
}

variable "program_text" {
  description = "(required) - Signalflow program text for the detector. More info at \"https://developers.signalfx.com/docs/signalflow-overview\""
  type        = string
}

variable "show_data_markers" {
  description = "(optional) - (true by default) When true, markers will be drawn for each datapoint within the visualization."
  type        = bool
  default     = null
}

variable "show_event_lines" {
  description = "(optional) - (false by default) When true, vertical lines will be drawn for each triggered event within the visualization."
  type        = bool
  default     = null
}

variable "start_time" {
  description = "(optional) - Seconds since epoch. Used for visualization"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Tags associated with the detector"
  type        = list(string)
  default     = null
}

variable "teams" {
  description = "(optional) - Team IDs to associate the detector to"
  type        = list(string)
  default     = null
}

variable "time_range" {
  description = "(optional) - Seconds to display in the visualization. This is a rolling range from the current time. Example: 3600 = `-1h`. Defaults to 3600"
  type        = number
  default     = null
}

variable "timezone" {
  description = "(optional) - The property value is a string that denotes the geographic region associated with the time zone, (e.g. Australia/Sydney)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      description           = string
      detect_label          = string
      disabled              = bool
      notifications         = list(string)
      parameterized_body    = string
      parameterized_subject = string
      runbook_url           = string
      severity              = string
      tip                   = string
    }
  ))
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
resource "signalfx_detector" "this" {
  authorized_writer_teams = var.authorized_writer_teams
  authorized_writer_users = var.authorized_writer_users
  description             = var.description
  disable_sampling        = var.disable_sampling
  end_time                = var.end_time
  max_delay               = var.max_delay
  min_delay               = var.min_delay
  name                    = var.name
  program_text            = var.program_text
  show_data_markers       = var.show_data_markers
  show_event_lines        = var.show_event_lines
  start_time              = var.start_time
  tags                    = var.tags
  teams                   = var.teams
  time_range              = var.time_range
  timezone                = var.timezone

  dynamic "rule" {
    for_each = var.rule
    content {
      description           = rule.value["description"]
      detect_label          = rule.value["detect_label"]
      disabled              = rule.value["disabled"]
      notifications         = rule.value["notifications"]
      parameterized_body    = rule.value["parameterized_body"]
      parameterized_subject = rule.value["parameterized_subject"]
      runbook_url           = rule.value["runbook_url"]
      severity              = rule.value["severity"]
      tip                   = rule.value["tip"]
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
  value       = signalfx_detector.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_detector.this.url
}

output "this" {
  value = signalfx_detector.this
}
```

[top](#index)