# google_eventarc_trigger

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
module "google_eventarc_trigger" {
  source = "./modules/google-beta/r/google_eventarc_trigger"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # service_account - (optional) is a type of string
  service_account = null

  destination = [{
    cloud_run_service = [{
      path    = null
      region  = null
      service = null
    }]
  }]

  matching_criteria = [{
    attribute = null
    value     = null
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cloud_run_service = list(object(
        {
          path    = string
          region  = string
          service = string
        }
      ))
    }
  ))
}

variable "matching_criteria" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      attribute = string
      value     = string
    }
  ))
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
resource "google_eventarc_trigger" "this" {
  location        = var.location
  name            = var.name
  project         = var.project
  service_account = var.service_account

  dynamic "destination" {
    for_each = var.destination
    content {

      dynamic "cloud_run_service" {
        for_each = destination.value.cloud_run_service
        content {
          path    = cloud_run_service.value["path"]
          region  = cloud_run_service.value["region"]
          service = cloud_run_service.value["service"]
        }
      }

    }
  }

  dynamic "matching_criteria" {
    for_each = var.matching_criteria
    content {
      attribute = matching_criteria.value["attribute"]
      value     = matching_criteria.value["value"]
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
output "create_time" {
  description = "returns a string"
  value       = google_eventarc_trigger.this.create_time
}

output "etag" {
  description = "returns a string"
  value       = google_eventarc_trigger.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_eventarc_trigger.this.id
}

output "project" {
  description = "returns a string"
  value       = google_eventarc_trigger.this.project
}

output "transport" {
  description = "returns a list of object"
  value       = google_eventarc_trigger.this.transport
}

output "update_time" {
  description = "returns a string"
  value       = google_eventarc_trigger.this.update_time
}

output "this" {
  value = google_eventarc_trigger.this
}
```

[top](#index)