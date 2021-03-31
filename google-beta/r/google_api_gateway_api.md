# google_api_gateway_api

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_api_gateway_api" {
  source = "./modules/google-beta/r/google_api_gateway_api"

  # api_id - (required) is a type of string
  api_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # managed_service - (optional) is a type of string
  managed_service = null
  # project - (optional) is a type of string
  project = null

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
variable "api_id" {
  description = "(required) - Identifier to assign to the API. Must be unique within scope of the parent resource(project)"
  type        = string
}

variable "display_name" {
  description = "(optional) - A user-visible name for the API."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user-provided metadata."
  type        = map(string)
  default     = null
}

variable "managed_service" {
  description = "(optional) - Immutable. The name of a Google Managed Service ( https://cloud.google.com/service-infrastructure/docs/glossary#managed).\nIf not specified, a new Service will automatically be created in the same project as this API."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "google_api_gateway_api" "this" {
  api_id          = var.api_id
  display_name    = var.display_name
  labels          = var.labels
  managed_service = var.managed_service
  project         = var.project

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
output "create_time" {
  description = "returns a string"
  value       = google_api_gateway_api.this.create_time
}

output "display_name" {
  description = "returns a string"
  value       = google_api_gateway_api.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_api_gateway_api.this.id
}

output "managed_service" {
  description = "returns a string"
  value       = google_api_gateway_api.this.managed_service
}

output "name" {
  description = "returns a string"
  value       = google_api_gateway_api.this.name
}

output "project" {
  description = "returns a string"
  value       = google_api_gateway_api.this.project
}

output "this" {
  value = google_api_gateway_api.this
}
```

[top](#index)