# google_monitoring_uptime_check_config

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
module "google_monitoring_uptime_check_config" {
  source = "./modules/google/r/google_monitoring_uptime_check_config"

  # display_name - (required) is a type of string
  display_name = null
  # period - (optional) is a type of string
  period = null
  # project - (optional) is a type of string
  project = null
  # selected_regions - (optional) is a type of list of string
  selected_regions = []
  # timeout - (required) is a type of string
  timeout = null

  content_matchers = [{
    content = null
    matcher = null
  }]

  http_check = [{
    auth_info = [{
      password = null
      username = null
    }]
    body           = null
    content_type   = null
    headers        = {}
    mask_headers   = null
    path           = null
    port           = null
    request_method = null
    use_ssl        = null
    validate_ssl   = null
  }]

  monitored_resource = [{
    labels = {}
    type   = null
  }]

  resource_group = [{
    group_id      = null
    resource_type = null
  }]

  tcp_check = [{
    port = null
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
variable "display_name" {
  description = "(required) - A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver Workspace in order to make it easier to identify; however, uniqueness is not enforced."
  type        = string
}

variable "period" {
  description = "(optional) - How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5 minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selected_regions" {
  description = "(optional) - The list of regions from which the check will be run. Some regions contain one location, and others contain more than one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error message is returned. Not specifying this field will result in uptime checks running from all regions."
  type        = list(string)
  default     = null
}

variable "timeout" {
  description = "(required) - The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration"
  type        = string
}

variable "content_matchers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      content = string
      matcher = string
    }
  ))
  default = []
}

variable "http_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_info = list(object(
        {
          password = string
          username = string
        }
      ))
      body           = string
      content_type   = string
      headers        = map(string)
      mask_headers   = bool
      path           = string
      port           = number
      request_method = string
      use_ssl        = bool
      validate_ssl   = bool
    }
  ))
  default = []
}

variable "monitored_resource" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      labels = map(string)
      type   = string
    }
  ))
  default = []
}

variable "resource_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group_id      = string
      resource_type = string
    }
  ))
  default = []
}

variable "tcp_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      port = number
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
resource "google_monitoring_uptime_check_config" "this" {
  display_name     = var.display_name
  period           = var.period
  project          = var.project
  selected_regions = var.selected_regions
  timeout          = var.timeout

  dynamic "content_matchers" {
    for_each = var.content_matchers
    content {
      content = content_matchers.value["content"]
      matcher = content_matchers.value["matcher"]
    }
  }

  dynamic "http_check" {
    for_each = var.http_check
    content {
      body           = http_check.value["body"]
      content_type   = http_check.value["content_type"]
      headers        = http_check.value["headers"]
      mask_headers   = http_check.value["mask_headers"]
      path           = http_check.value["path"]
      port           = http_check.value["port"]
      request_method = http_check.value["request_method"]
      use_ssl        = http_check.value["use_ssl"]
      validate_ssl   = http_check.value["validate_ssl"]

      dynamic "auth_info" {
        for_each = http_check.value.auth_info
        content {
          password = auth_info.value["password"]
          username = auth_info.value["username"]
        }
      }

    }
  }

  dynamic "monitored_resource" {
    for_each = var.monitored_resource
    content {
      labels = monitored_resource.value["labels"]
      type   = monitored_resource.value["type"]
    }
  }

  dynamic "resource_group" {
    for_each = var.resource_group
    content {
      group_id      = resource_group.value["group_id"]
      resource_type = resource_group.value["resource_type"]
    }
  }

  dynamic "tcp_check" {
    for_each = var.tcp_check
    content {
      port = tcp_check.value["port"]
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
output "id" {
  description = "returns a string"
  value       = google_monitoring_uptime_check_config.this.id
}

output "name" {
  description = "returns a string"
  value       = google_monitoring_uptime_check_config.this.name
}

output "project" {
  description = "returns a string"
  value       = google_monitoring_uptime_check_config.this.project
}

output "uptime_check_id" {
  description = "returns a string"
  value       = google_monitoring_uptime_check_config.this.uptime_check_id
}

output "this" {
  value = google_monitoring_uptime_check_config.this
}
```

[top](#index)