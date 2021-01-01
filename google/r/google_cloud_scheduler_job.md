# google_cloud_scheduler_job

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
module "google_cloud_scheduler_job" {
  source = "./modules/google/r/google_cloud_scheduler_job"

  # attempt_deadline - (optional) is a type of string
  attempt_deadline = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # schedule - (optional) is a type of string
  schedule = null
  # time_zone - (optional) is a type of string
  time_zone = null

  app_engine_http_target = [{
    app_engine_routing = [{
      instance = null
      service  = null
      version  = null
    }]
    body         = null
    headers      = {}
    http_method  = null
    relative_uri = null
  }]

  http_target = [{
    body        = null
    headers     = {}
    http_method = null
    oauth_token = [{
      scope                 = null
      service_account_email = null
    }]
    oidc_token = [{
      audience              = null
      service_account_email = null
    }]
    uri = null
  }]

  pubsub_target = [{
    attributes = {}
    data       = null
    topic_name = null
  }]

  retry_config = [{
    max_backoff_duration = null
    max_doublings        = null
    max_retry_duration   = null
    min_backoff_duration = null
    retry_count          = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "attempt_deadline" {
  description = "(optional) - The deadline for job attempts. If the request handler does not respond by this deadline then the request is\ncancelled and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in\nexecution logs. Cloud Scheduler will retry the job according to the RetryConfig.\nThe allowed duration for this deadline is:\n* For HTTP targets, between 15 seconds and 30 minutes.\n* For App Engine HTTP targets, between 15 seconds and 24 hours.\n* **Note**: For PubSub targets, this field is ignored - setting it will introduce an unresolvable diff.\nA duration in seconds with up to nine fractional digits, terminated by 's'. Example: \"3.5s\""
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - A human-readable description for the job. \nThis string must not contain more than 500 characters."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the job."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the scheduler job resides. If it is not provided, Terraform will use the provider default."
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional) - Describes the schedule on which the job will be executed."
  type        = string
  default     = null
}

variable "time_zone" {
  description = "(optional) - Specifies the time zone to be used in interpreting schedule.\nThe value of this field must be a time zone name from the tz database."
  type        = string
  default     = null
}

variable "app_engine_http_target" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      app_engine_routing = list(object(
        {
          instance = string
          service  = string
          version  = string
        }
      ))
      body         = string
      headers      = map(string)
      http_method  = string
      relative_uri = string
    }
  ))
  default = []
}

variable "http_target" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      body        = string
      headers     = map(string)
      http_method = string
      oauth_token = list(object(
        {
          scope                 = string
          service_account_email = string
        }
      ))
      oidc_token = list(object(
        {
          audience              = string
          service_account_email = string
        }
      ))
      uri = string
    }
  ))
  default = []
}

variable "pubsub_target" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attributes = map(string)
      data       = string
      topic_name = string
    }
  ))
  default = []
}

variable "retry_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_backoff_duration = string
      max_doublings        = number
      max_retry_duration   = string
      min_backoff_duration = string
      retry_count          = number
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_cloud_scheduler_job" "this" {
  attempt_deadline = var.attempt_deadline
  description      = var.description
  name             = var.name
  project          = var.project
  region           = var.region
  schedule         = var.schedule
  time_zone        = var.time_zone

  dynamic "app_engine_http_target" {
    for_each = var.app_engine_http_target
    content {
      body         = app_engine_http_target.value["body"]
      headers      = app_engine_http_target.value["headers"]
      http_method  = app_engine_http_target.value["http_method"]
      relative_uri = app_engine_http_target.value["relative_uri"]

      dynamic "app_engine_routing" {
        for_each = app_engine_http_target.value.app_engine_routing
        content {
          instance = app_engine_routing.value["instance"]
          service  = app_engine_routing.value["service"]
          version  = app_engine_routing.value["version"]
        }
      }

    }
  }

  dynamic "http_target" {
    for_each = var.http_target
    content {
      body        = http_target.value["body"]
      headers     = http_target.value["headers"]
      http_method = http_target.value["http_method"]
      uri         = http_target.value["uri"]

      dynamic "oauth_token" {
        for_each = http_target.value.oauth_token
        content {
          scope                 = oauth_token.value["scope"]
          service_account_email = oauth_token.value["service_account_email"]
        }
      }

      dynamic "oidc_token" {
        for_each = http_target.value.oidc_token
        content {
          audience              = oidc_token.value["audience"]
          service_account_email = oidc_token.value["service_account_email"]
        }
      }

    }
  }

  dynamic "pubsub_target" {
    for_each = var.pubsub_target
    content {
      attributes = pubsub_target.value["attributes"]
      data       = pubsub_target.value["data"]
      topic_name = pubsub_target.value["topic_name"]
    }
  }

  dynamic "retry_config" {
    for_each = var.retry_config
    content {
      max_backoff_duration = retry_config.value["max_backoff_duration"]
      max_doublings        = retry_config.value["max_doublings"]
      max_retry_duration   = retry_config.value["max_retry_duration"]
      min_backoff_duration = retry_config.value["min_backoff_duration"]
      retry_count          = retry_config.value["retry_count"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_cloud_scheduler_job.this.id
}

output "project" {
  description = "returns a string"
  value       = google_cloud_scheduler_job.this.project
}

output "region" {
  description = "returns a string"
  value       = google_cloud_scheduler_job.this.region
}

output "this" {
  value = google_cloud_scheduler_job.this
}
```

[top](#index)