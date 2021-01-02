# google_app_engine_application

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
module "google_app_engine_application" {
  source = "./modules/google/r/google_app_engine_application"

  # auth_domain - (optional) is a type of string
  auth_domain = null
  # database_type - (optional) is a type of string
  database_type = null
  # location_id - (required) is a type of string
  location_id = null
  # project - (optional) is a type of string
  project = null
  # serving_status - (optional) is a type of string
  serving_status = null

  feature_settings = [{
    split_health_checks = null
  }]

  iap = [{
    enabled                     = null
    oauth2_client_id            = null
    oauth2_client_secret        = null
    oauth2_client_secret_sha256 = null
  }]

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_domain" {
  description = "(optional) - The domain to authenticate users with when using App Engine's User API."
  type        = string
  default     = null
}

variable "database_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location_id" {
  description = "(required) - The location to serve the app from."
  type        = string
}

variable "project" {
  description = "(optional) - The project ID to create the application under."
  type        = string
  default     = null
}

variable "serving_status" {
  description = "(optional) - The serving status of the app."
  type        = string
  default     = null
}

variable "feature_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      split_health_checks = bool
    }
  ))
  default = []
}

variable "iap" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled                     = bool
      oauth2_client_id            = string
      oauth2_client_secret        = string
      oauth2_client_secret_sha256 = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_app_engine_application" "this" {
  auth_domain    = var.auth_domain
  database_type  = var.database_type
  location_id    = var.location_id
  project        = var.project
  serving_status = var.serving_status

  dynamic "feature_settings" {
    for_each = var.feature_settings
    content {
      split_health_checks = feature_settings.value["split_health_checks"]
    }
  }

  dynamic "iap" {
    for_each = var.iap
    content {
      enabled              = iap.value["enabled"]
      oauth2_client_id     = iap.value["oauth2_client_id"]
      oauth2_client_secret = iap.value["oauth2_client_secret"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_id" {
  description = "returns a string"
  value       = google_app_engine_application.this.app_id
}

output "auth_domain" {
  description = "returns a string"
  value       = google_app_engine_application.this.auth_domain
}

output "code_bucket" {
  description = "returns a string"
  value       = google_app_engine_application.this.code_bucket
}

output "database_type" {
  description = "returns a string"
  value       = google_app_engine_application.this.database_type
}

output "default_bucket" {
  description = "returns a string"
  value       = google_app_engine_application.this.default_bucket
}

output "default_hostname" {
  description = "returns a string"
  value       = google_app_engine_application.this.default_hostname
}

output "gcr_domain" {
  description = "returns a string"
  value       = google_app_engine_application.this.gcr_domain
}

output "id" {
  description = "returns a string"
  value       = google_app_engine_application.this.id
}

output "name" {
  description = "returns a string"
  value       = google_app_engine_application.this.name
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_application.this.project
}

output "serving_status" {
  description = "returns a string"
  value       = google_app_engine_application.this.serving_status
}

output "url_dispatch_rule" {
  description = "returns a list of object"
  value       = google_app_engine_application.this.url_dispatch_rule
}

output "this" {
  value = google_app_engine_application.this
}
```

[top](#index)