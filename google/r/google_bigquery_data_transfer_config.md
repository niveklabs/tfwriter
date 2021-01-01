# google_bigquery_data_transfer_config

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_bigquery_data_transfer_config" {
  source = "./modules/google/r/google_bigquery_data_transfer_config"

  # data_refresh_window_days - (optional) is a type of number
  data_refresh_window_days = null
  # data_source_id - (required) is a type of string
  data_source_id = null
  # destination_dataset_id - (required) is a type of string
  destination_dataset_id = null
  # disabled - (optional) is a type of bool
  disabled = null
  # display_name - (required) is a type of string
  display_name = null
  # location - (optional) is a type of string
  location = null
  # notification_pubsub_topic - (optional) is a type of string
  notification_pubsub_topic = null
  # params - (required) is a type of map of string
  params = {}
  # project - (optional) is a type of string
  project = null
  # schedule - (optional) is a type of string
  schedule = null
  # service_account_name - (optional) is a type of string
  service_account_name = null

  email_preferences = [{
    enable_failure_email = null
  }]

  schedule_options = [{
    disable_auto_scheduling = null
    end_time                = null
    start_time              = null
  }]

  sensitive_params = [{
    secret_access_key = null
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

```hcl
variable "data_refresh_window_days" {
  description = "(optional) - The number of days to look back to automatically refresh the data.\nFor example, if dataRefreshWindowDays = 10, then every day BigQuery\nreingests data for [today-10, today-1], rather than ingesting data for\njust [today-1]. Only valid if the data source supports the feature.\nSet the value to 0 to use the default value."
  type        = number
  default     = null
}

variable "data_source_id" {
  description = "(required) - The data source id. Cannot be changed once the transfer config is created."
  type        = string
}

variable "destination_dataset_id" {
  description = "(required) - The BigQuery target dataset id."
  type        = string
}

variable "disabled" {
  description = "(optional) - When set to true, no runs are scheduled for a given transfer."
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(required) - The user specified display name for the transfer config."
  type        = string
}

variable "location" {
  description = "(optional) - The geographic location where the transfer config should reside.\nExamples: US, EU, asia-northeast1. The default value is US."
  type        = string
  default     = null
}

variable "notification_pubsub_topic" {
  description = "(optional) - Pub/Sub topic where notifications will be sent after transfer runs\nassociated with this transfer config finish."
  type        = string
  default     = null
}

variable "params" {
  description = "(required) - These parameters are specific to each data source."
  type        = map(string)
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional) - Data transfer schedule. If the data source does not support a custom\nschedule, this should be empty. If it is empty, the default value for\nthe data source will be used. The specified times are in UTC. Examples\nof valid format: 1st,3rd monday of month 15:30, every wed,fri of jan,\njun 13:15, and first sunday of quarter 00:00. See more explanation\nabout the format here:\nhttps://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format\nNOTE: the granularity should be at least 8 hours, or less frequent."
  type        = string
  default     = null
}

variable "service_account_name" {
  description = "(optional) - Optional service account name. If this field is set, transfer config will\nbe created with this service account credentials. It requires that\nrequesting user calling this API has permissions to act as this service account."
  type        = string
  default     = null
}

variable "email_preferences" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_failure_email = bool
    }
  ))
  default = []
}

variable "schedule_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable_auto_scheduling = bool
      end_time                = string
      start_time              = string
    }
  ))
  default = []
}

variable "sensitive_params" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      secret_access_key = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_bigquery_data_transfer_config" "this" {
  data_refresh_window_days  = var.data_refresh_window_days
  data_source_id            = var.data_source_id
  destination_dataset_id    = var.destination_dataset_id
  disabled                  = var.disabled
  display_name              = var.display_name
  location                  = var.location
  notification_pubsub_topic = var.notification_pubsub_topic
  params                    = var.params
  project                   = var.project
  schedule                  = var.schedule
  service_account_name      = var.service_account_name

  dynamic "email_preferences" {
    for_each = var.email_preferences
    content {
      enable_failure_email = email_preferences.value["enable_failure_email"]
    }
  }

  dynamic "schedule_options" {
    for_each = var.schedule_options
    content {
      disable_auto_scheduling = schedule_options.value["disable_auto_scheduling"]
      end_time                = schedule_options.value["end_time"]
      start_time              = schedule_options.value["start_time"]
    }
  }

  dynamic "sensitive_params" {
    for_each = var.sensitive_params
    content {
      secret_access_key = sensitive_params.value["secret_access_key"]
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

```hcl
output "id" {
  description = "returns a string"
  value       = google_bigquery_data_transfer_config.this.id
}

output "name" {
  description = "returns a string"
  value       = google_bigquery_data_transfer_config.this.name
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_data_transfer_config.this.project
}

output "this" {
  value = google_bigquery_data_transfer_config.this
}
```

[top](#index)