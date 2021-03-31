# google_monitoring_alert_policy

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_monitoring_alert_policy" {
  source = "./modules/google/r/google_monitoring_alert_policy"

  # combiner - (required) is a type of string
  combiner = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # notification_channels - (optional) is a type of list of string
  notification_channels = []
  # project - (optional) is a type of string
  project = null
  # user_labels - (optional) is a type of map of string
  user_labels = {}

  conditions = [{
    condition_absent = [{
      aggregations = [{
        alignment_period     = null
        cross_series_reducer = null
        group_by_fields      = []
        per_series_aligner   = null
      }]
      duration = null
      filter   = null
      trigger = [{
        count   = null
        percent = null
      }]
    }]
    condition_monitoring_query_language = [{
      duration = null
      query    = null
      trigger = [{
        count   = null
        percent = null
      }]
    }]
    condition_threshold = [{
      aggregations = [{
        alignment_period     = null
        cross_series_reducer = null
        group_by_fields      = []
        per_series_aligner   = null
      }]
      comparison = null
      denominator_aggregations = [{
        alignment_period     = null
        cross_series_reducer = null
        group_by_fields      = []
        per_series_aligner   = null
      }]
      denominator_filter = null
      duration           = null
      filter             = null
      threshold_value    = null
      trigger = [{
        count   = null
        percent = null
      }]
    }]
    display_name = null
    name         = null
  }]

  documentation = [{
    content   = null
    mime_type = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "combiner" {
  description = "(required) - How to combine the results of multiple conditions to\ndetermine if an incident should be opened. Possible values: [\"AND\", \"OR\", \"AND_WITH_MATCHING_RESOURCE\"]"
  type        = string
}

variable "display_name" {
  description = "(required) - A short name or phrase used to identify the policy in\ndashboards, notifications, and incidents. To avoid confusion, don't use\nthe same display name for multiple policies in the same project. The\nname is limited to 512 Unicode characters."
  type        = string
}

variable "enabled" {
  description = "(optional) - Whether or not the policy is enabled. The default is true."
  type        = bool
  default     = null
}

variable "notification_channels" {
  description = "(optional) - Identifies the notification channels to which notifications should be\nsent when incidents are opened or closed or when new violations occur\non an already opened incident. Each element of this array corresponds\nto the name field in each of the NotificationChannel objects that are\nreturned from the notificationChannels.list method. The syntax of the\nentries in this field is\n'projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]'"
  type        = list(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_labels" {
  description = "(optional) - This field is intended to be used for organizing and identifying the AlertPolicy\nobjects.The field can contain up to 64 entries. Each key and value is limited\nto 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values\ncan contain only lowercase letters, numerals, underscores, and dashes. Keys\nmust begin with a letter."
  type        = map(string)
  default     = null
}

variable "conditions" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      condition_absent = list(object(
        {
          aggregations = list(object(
            {
              alignment_period     = string
              cross_series_reducer = string
              group_by_fields      = list(string)
              per_series_aligner   = string
            }
          ))
          duration = string
          filter   = string
          trigger = list(object(
            {
              count   = number
              percent = number
            }
          ))
        }
      ))
      condition_monitoring_query_language = list(object(
        {
          duration = string
          query    = string
          trigger = list(object(
            {
              count   = number
              percent = number
            }
          ))
        }
      ))
      condition_threshold = list(object(
        {
          aggregations = list(object(
            {
              alignment_period     = string
              cross_series_reducer = string
              group_by_fields      = list(string)
              per_series_aligner   = string
            }
          ))
          comparison = string
          denominator_aggregations = list(object(
            {
              alignment_period     = string
              cross_series_reducer = string
              group_by_fields      = list(string)
              per_series_aligner   = string
            }
          ))
          denominator_filter = string
          duration           = string
          filter             = string
          threshold_value    = number
          trigger = list(object(
            {
              count   = number
              percent = number
            }
          ))
        }
      ))
      display_name = string
      name         = string
    }
  ))
}

variable "documentation" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content   = string
      mime_type = string
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
```

[top](#index)

### Resource

```terraform
resource "google_monitoring_alert_policy" "this" {
  combiner              = var.combiner
  display_name          = var.display_name
  enabled               = var.enabled
  notification_channels = var.notification_channels
  project               = var.project
  user_labels           = var.user_labels

  dynamic "conditions" {
    for_each = var.conditions
    content {
      display_name = conditions.value["display_name"]

      dynamic "condition_absent" {
        for_each = conditions.value.condition_absent
        content {
          duration = condition_absent.value["duration"]
          filter   = condition_absent.value["filter"]

          dynamic "aggregations" {
            for_each = condition_absent.value.aggregations
            content {
              alignment_period     = aggregations.value["alignment_period"]
              cross_series_reducer = aggregations.value["cross_series_reducer"]
              group_by_fields      = aggregations.value["group_by_fields"]
              per_series_aligner   = aggregations.value["per_series_aligner"]
            }
          }

          dynamic "trigger" {
            for_each = condition_absent.value.trigger
            content {
              count   = trigger.value["count"]
              percent = trigger.value["percent"]
            }
          }

        }
      }

      dynamic "condition_monitoring_query_language" {
        for_each = conditions.value.condition_monitoring_query_language
        content {
          duration = condition_monitoring_query_language.value["duration"]
          query    = condition_monitoring_query_language.value["query"]

          dynamic "trigger" {
            for_each = condition_monitoring_query_language.value.trigger
            content {
              count   = trigger.value["count"]
              percent = trigger.value["percent"]
            }
          }

        }
      }

      dynamic "condition_threshold" {
        for_each = conditions.value.condition_threshold
        content {
          comparison         = condition_threshold.value["comparison"]
          denominator_filter = condition_threshold.value["denominator_filter"]
          duration           = condition_threshold.value["duration"]
          filter             = condition_threshold.value["filter"]
          threshold_value    = condition_threshold.value["threshold_value"]

          dynamic "aggregations" {
            for_each = condition_threshold.value.aggregations
            content {
              alignment_period     = aggregations.value["alignment_period"]
              cross_series_reducer = aggregations.value["cross_series_reducer"]
              group_by_fields      = aggregations.value["group_by_fields"]
              per_series_aligner   = aggregations.value["per_series_aligner"]
            }
          }

          dynamic "denominator_aggregations" {
            for_each = condition_threshold.value.denominator_aggregations
            content {
              alignment_period     = denominator_aggregations.value["alignment_period"]
              cross_series_reducer = denominator_aggregations.value["cross_series_reducer"]
              group_by_fields      = denominator_aggregations.value["group_by_fields"]
              per_series_aligner   = denominator_aggregations.value["per_series_aligner"]
            }
          }

          dynamic "trigger" {
            for_each = condition_threshold.value.trigger
            content {
              count   = trigger.value["count"]
              percent = trigger.value["percent"]
            }
          }

        }
      }

    }
  }

  dynamic "documentation" {
    for_each = var.documentation
    content {
      content   = documentation.value["content"]
      mime_type = documentation.value["mime_type"]
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

}
```

[top](#index)

### Outputs

```terraform
output "creation_record" {
  description = "returns a list of object"
  value       = google_monitoring_alert_policy.this.creation_record
}

output "id" {
  description = "returns a string"
  value       = google_monitoring_alert_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = google_monitoring_alert_policy.this.name
}

output "project" {
  description = "returns a string"
  value       = google_monitoring_alert_policy.this.project
}

output "this" {
  value = google_monitoring_alert_policy.this
}
```

[top](#index)