# google_service_usage_consumer_quota_override

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_service_usage_consumer_quota_override" {
  source = "./modules/google-beta/r/google_service_usage_consumer_quota_override"

  # dimensions - (optional) is a type of map of string
  dimensions = {}
  # force - (optional) is a type of bool
  force = null
  # limit - (required) is a type of string
  limit = null
  # metric - (required) is a type of string
  metric = null
  # override_value - (required) is a type of string
  override_value = null
  # project - (optional) is a type of string
  project = null
  # service - (required) is a type of string
  service = null

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
variable "dimensions" {
  description = "(optional) - If this map is nonempty, then this override applies only to specific values for dimensions defined in the limit unit."
  type        = map(string)
  default     = null
}

variable "force" {
  description = "(optional) - If the new quota would decrease the existing quota by more than 10%, the request is rejected.\nIf 'force' is 'true', that safety check is ignored."
  type        = bool
  default     = null
}

variable "limit" {
  description = "(required) - The limit on the metric, e.g. '/project/region'."
  type        = string
}

variable "metric" {
  description = "(required) - The metric that should be limited, e.g. 'compute.googleapis.com/cpus'."
  type        = string
}

variable "override_value" {
  description = "(required) - The overriding quota limit value. Can be any nonnegative integer, or -1 (unlimited quota)."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "(required) - The service that the metrics belong to, e.g. 'compute.googleapis.com'."
  type        = string
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
resource "google_service_usage_consumer_quota_override" "this" {
  dimensions     = var.dimensions
  force          = var.force
  limit          = var.limit
  metric         = var.metric
  override_value = var.override_value
  project        = var.project
  service        = var.service

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
  value       = google_service_usage_consumer_quota_override.this.id
}

output "name" {
  description = "returns a string"
  value       = google_service_usage_consumer_quota_override.this.name
}

output "project" {
  description = "returns a string"
  value       = google_service_usage_consumer_quota_override.this.project
}

output "this" {
  value = google_service_usage_consumer_quota_override.this
}
```

[top](#index)