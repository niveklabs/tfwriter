# google_cloud_tasks_queue

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_cloud_tasks_queue" {
  source = "./modules/google/r/google_cloud_tasks_queue"

  # location - (required) is a type of string
  location = null
  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  app_engine_routing_override = [{
    host     = null
    instance = null
    service  = null
    version  = null
  }]

  rate_limits = [{
    max_burst_size            = null
    max_concurrent_dispatches = null
    max_dispatches_per_second = null
  }]

  retry_config = [{
    max_attempts       = null
    max_backoff        = null
    max_doublings      = null
    max_retry_duration = null
    min_backoff        = null
  }]

  stackdriver_logging_config = [{
    sampling_ratio = null
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
variable "location" {
  description = "(required) - The location of the queue"
  type        = string
}

variable "name" {
  description = "(optional) - The queue name."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_engine_routing_override" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      host     = string
      instance = string
      service  = string
      version  = string
    }
  ))
  default = []
}

variable "rate_limits" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_burst_size            = number
      max_concurrent_dispatches = number
      max_dispatches_per_second = number
    }
  ))
  default = []
}

variable "retry_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_attempts       = number
      max_backoff        = string
      max_doublings      = number
      max_retry_duration = string
      min_backoff        = string
    }
  ))
  default = []
}

variable "stackdriver_logging_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      sampling_ratio = number
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
resource "google_cloud_tasks_queue" "this" {
  location = var.location
  name     = var.name
  project  = var.project

  dynamic "app_engine_routing_override" {
    for_each = var.app_engine_routing_override
    content {
      instance = app_engine_routing_override.value["instance"]
      service  = app_engine_routing_override.value["service"]
      version  = app_engine_routing_override.value["version"]
    }
  }

  dynamic "rate_limits" {
    for_each = var.rate_limits
    content {
      max_concurrent_dispatches = rate_limits.value["max_concurrent_dispatches"]
      max_dispatches_per_second = rate_limits.value["max_dispatches_per_second"]
    }
  }

  dynamic "retry_config" {
    for_each = var.retry_config
    content {
      max_attempts       = retry_config.value["max_attempts"]
      max_backoff        = retry_config.value["max_backoff"]
      max_doublings      = retry_config.value["max_doublings"]
      max_retry_duration = retry_config.value["max_retry_duration"]
      min_backoff        = retry_config.value["min_backoff"]
    }
  }

  dynamic "stackdriver_logging_config" {
    for_each = var.stackdriver_logging_config
    content {
      sampling_ratio = stackdriver_logging_config.value["sampling_ratio"]
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
  value       = google_cloud_tasks_queue.this.id
}

output "project" {
  description = "returns a string"
  value       = google_cloud_tasks_queue.this.project
}

output "this" {
  value = google_cloud_tasks_queue.this
}
```

[top](#index)