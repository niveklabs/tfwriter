# google_monitoring_slo

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_monitoring_slo" {
  source = "./modules/google/r/google_monitoring_slo"

  # calendar_period - (optional) is a type of string
  calendar_period = null
  # display_name - (optional) is a type of string
  display_name = null
  # goal - (required) is a type of number
  goal = null
  # project - (optional) is a type of string
  project = null
  # rolling_period_days - (optional) is a type of number
  rolling_period_days = null
  # service - (required) is a type of string
  service = null
  # slo_id - (optional) is a type of string
  slo_id = null

  basic_sli = [{
    latency = [{
      threshold = null
    }]
    location = []
    method   = []
    version  = []
  }]

  request_based_sli = [{
    distribution_cut = [{
      distribution_filter = null
      range = [{
        max = null
        min = null
      }]
    }]
    good_total_ratio = [{
      bad_service_filter   = null
      good_service_filter  = null
      total_service_filter = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  windows_based_sli = [{
    good_bad_metric_filter = null
    good_total_ratio_threshold = [{
      basic_sli_performance = [{
        latency = [{
          threshold = null
        }]
        location = []
        method   = []
        version  = []
      }]
      performance = [{
        distribution_cut = [{
          distribution_filter = null
          range = [{
            max = null
            min = null
          }]
        }]
        good_total_ratio = [{
          bad_service_filter   = null
          good_service_filter  = null
          total_service_filter = null
        }]
      }]
      threshold = null
    }]
    metric_mean_in_range = [{
      range = [{
        max = null
        min = null
      }]
      time_series = null
    }]
    metric_sum_in_range = [{
      range = [{
        max = null
        min = null
      }]
      time_series = null
    }]
    window_period = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "calendar_period" {
  description = "(optional) - A calendar period, semantically \"since the start of the current\n<calendarPeriod>\". Possible values: [\"DAY\", \"WEEK\", \"FORTNIGHT\", \"MONTH\"]"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Name used for UI elements listing this SLO."
  type        = string
  default     = null
}

variable "goal" {
  description = "(required) - The fraction of service that must be good in order for this objective\nto be met. 0 < goal <= 0.999"
  type        = number
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rolling_period_days" {
  description = "(optional) - A rolling time period, semantically \"in the past X days\".\nMust be between 1 to 30 days, inclusive."
  type        = number
  default     = null
}

variable "service" {
  description = "(required) - ID of the service to which this SLO belongs."
  type        = string
}

variable "slo_id" {
  description = "(optional) - The id to use for this ServiceLevelObjective. If omitted, an id will be generated instead."
  type        = string
  default     = null
}

variable "basic_sli" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      latency = list(object(
        {
          threshold = string
        }
      ))
      location = set(string)
      method   = set(string)
      version  = set(string)
    }
  ))
  default = []
}

variable "request_based_sli" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      distribution_cut = list(object(
        {
          distribution_filter = string
          range = list(object(
            {
              max = number
              min = number
            }
          ))
        }
      ))
      good_total_ratio = list(object(
        {
          bad_service_filter   = string
          good_service_filter  = string
          total_service_filter = string
        }
      ))
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "windows_based_sli" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      good_bad_metric_filter = string
      good_total_ratio_threshold = list(object(
        {
          basic_sli_performance = list(object(
            {
              latency = list(object(
                {
                  threshold = string
                }
              ))
              location = set(string)
              method   = set(string)
              version  = set(string)
            }
          ))
          performance = list(object(
            {
              distribution_cut = list(object(
                {
                  distribution_filter = string
                  range = list(object(
                    {
                      max = number
                      min = number
                    }
                  ))
                }
              ))
              good_total_ratio = list(object(
                {
                  bad_service_filter   = string
                  good_service_filter  = string
                  total_service_filter = string
                }
              ))
            }
          ))
          threshold = number
        }
      ))
      metric_mean_in_range = list(object(
        {
          range = list(object(
            {
              max = number
              min = number
            }
          ))
          time_series = string
        }
      ))
      metric_sum_in_range = list(object(
        {
          range = list(object(
            {
              max = number
              min = number
            }
          ))
          time_series = string
        }
      ))
      window_period = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_monitoring_slo" "this" {
  calendar_period     = var.calendar_period
  display_name        = var.display_name
  goal                = var.goal
  project             = var.project
  rolling_period_days = var.rolling_period_days
  service             = var.service
  slo_id              = var.slo_id

  dynamic "basic_sli" {
    for_each = var.basic_sli
    content {
      location = basic_sli.value["location"]
      method   = basic_sli.value["method"]
      version  = basic_sli.value["version"]

      dynamic "latency" {
        for_each = basic_sli.value.latency
        content {
          threshold = latency.value["threshold"]
        }
      }

    }
  }

  dynamic "request_based_sli" {
    for_each = var.request_based_sli
    content {

      dynamic "distribution_cut" {
        for_each = request_based_sli.value.distribution_cut
        content {
          distribution_filter = distribution_cut.value["distribution_filter"]

          dynamic "range" {
            for_each = distribution_cut.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
            }
          }

        }
      }

      dynamic "good_total_ratio" {
        for_each = request_based_sli.value.good_total_ratio
        content {
          bad_service_filter   = good_total_ratio.value["bad_service_filter"]
          good_service_filter  = good_total_ratio.value["good_service_filter"]
          total_service_filter = good_total_ratio.value["total_service_filter"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "windows_based_sli" {
    for_each = var.windows_based_sli
    content {
      good_bad_metric_filter = windows_based_sli.value["good_bad_metric_filter"]
      window_period          = windows_based_sli.value["window_period"]

      dynamic "good_total_ratio_threshold" {
        for_each = windows_based_sli.value.good_total_ratio_threshold
        content {
          threshold = good_total_ratio_threshold.value["threshold"]

          dynamic "basic_sli_performance" {
            for_each = good_total_ratio_threshold.value.basic_sli_performance
            content {
              location = basic_sli_performance.value["location"]
              method   = basic_sli_performance.value["method"]
              version  = basic_sli_performance.value["version"]

              dynamic "latency" {
                for_each = basic_sli_performance.value.latency
                content {
                  threshold = latency.value["threshold"]
                }
              }

            }
          }

          dynamic "performance" {
            for_each = good_total_ratio_threshold.value.performance
            content {

              dynamic "distribution_cut" {
                for_each = performance.value.distribution_cut
                content {
                  distribution_filter = distribution_cut.value["distribution_filter"]

                  dynamic "range" {
                    for_each = distribution_cut.value.range
                    content {
                      max = range.value["max"]
                      min = range.value["min"]
                    }
                  }

                }
              }

              dynamic "good_total_ratio" {
                for_each = performance.value.good_total_ratio
                content {
                  bad_service_filter   = good_total_ratio.value["bad_service_filter"]
                  good_service_filter  = good_total_ratio.value["good_service_filter"]
                  total_service_filter = good_total_ratio.value["total_service_filter"]
                }
              }

            }
          }

        }
      }

      dynamic "metric_mean_in_range" {
        for_each = windows_based_sli.value.metric_mean_in_range
        content {
          time_series = metric_mean_in_range.value["time_series"]

          dynamic "range" {
            for_each = metric_mean_in_range.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
            }
          }

        }
      }

      dynamic "metric_sum_in_range" {
        for_each = windows_based_sli.value.metric_sum_in_range
        content {
          time_series = metric_sum_in_range.value["time_series"]

          dynamic "range" {
            for_each = metric_sum_in_range.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
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
  value       = google_monitoring_slo.this.id
}

output "name" {
  description = "returns a string"
  value       = google_monitoring_slo.this.name
}

output "project" {
  description = "returns a string"
  value       = google_monitoring_slo.this.project
}

output "slo_id" {
  description = "returns a string"
  value       = google_monitoring_slo.this.slo_id
}

output "this" {
  value = google_monitoring_slo.this
}
```

[top](#index)