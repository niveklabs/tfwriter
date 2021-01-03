# google_monitoring_custom_service

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
module "google_monitoring_custom_service" {
  source = "./modules/google-beta/r/google_monitoring_custom_service"

  # display_name - (optional) is a type of string
  display_name = null
  # project - (optional) is a type of string
  project = null
  # service_id - (optional) is a type of string
  service_id = null

  telemetry = [{
    resource_name = null
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
  description = "(optional) - Name used for UI elements listing this Service."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_id" {
  description = "(optional) - An optional service ID to use. If not given, the server will generate a\nservice ID."
  type        = string
  default     = null
}

variable "telemetry" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      resource_name = string
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
resource "google_monitoring_custom_service" "this" {
  display_name = var.display_name
  project      = var.project
  service_id   = var.service_id

  dynamic "telemetry" {
    for_each = var.telemetry
    content {
      resource_name = telemetry.value["resource_name"]
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
  value       = google_monitoring_custom_service.this.id
}

output "name" {
  description = "returns a string"
  value       = google_monitoring_custom_service.this.name
}

output "project" {
  description = "returns a string"
  value       = google_monitoring_custom_service.this.project
}

output "service_id" {
  description = "returns a string"
  value       = google_monitoring_custom_service.this.service_id
}

output "this" {
  value = google_monitoring_custom_service.this
}
```

[top](#index)