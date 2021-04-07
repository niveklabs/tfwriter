# google_monitoring_app_engine_service

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_monitoring_app_engine_service" {
  source = "./modules/google/d/google_monitoring_app_engine_service"

  # module_id - (required) is a type of string
  module_id = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "module_id" {
  description = "(required) - The ID of the App Engine module underlying this service. \nCorresponds to the 'moduleId' resource label for a 'gae_app'\nmonitored resource(see https://cloud.google.com/monitoring/api/resources#tag_gae_app)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_monitoring_app_engine_service" "this" {
  # module_id - (required) is a type of string
  module_id = var.module_id
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_monitoring_app_engine_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_monitoring_app_engine_service.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_monitoring_app_engine_service.this.name
}

output "service_id" {
  description = "returns a string"
  value       = data.google_monitoring_app_engine_service.this.service_id
}

output "telemetry" {
  description = "returns a list of object"
  value       = data.google_monitoring_app_engine_service.this.telemetry
}

output "this" {
  value = google_monitoring_app_engine_service.this
}
```

[top](#index)