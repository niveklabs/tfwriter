# google_bigquery_reservation

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
module "google_bigquery_reservation" {
  source = "./modules/google-beta/r/google_bigquery_reservation"

  # ignore_idle_slots - (optional) is a type of bool
  ignore_idle_slots = null
  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # slot_capacity - (required) is a type of number
  slot_capacity = null

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
variable "ignore_idle_slots" {
  description = "(optional) - If false, any query using this reservation will use idle slots from other reservations within\nthe same admin project. If true, a query using this reservation will execute with the slot\ncapacity specified above at most."
  type        = bool
  default     = null
}

variable "location" {
  description = "(optional) - The geographic location where the transfer config should reside.\nExamples: US, EU, asia-northeast1. The default value is US."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the reservation. This field must only contain alphanumeric characters or dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "slot_capacity" {
  description = "(required) - Minimum slots available to this reservation. A slot is a unit of computational power in BigQuery, and serves as the\nunit of parallelism. Queries using this reservation might use more slots during runtime if ignoreIdleSlots is set to false."
  type        = number
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
resource "google_bigquery_reservation" "this" {
  ignore_idle_slots = var.ignore_idle_slots
  location          = var.location
  name              = var.name
  project           = var.project
  slot_capacity     = var.slot_capacity

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
  value       = google_bigquery_reservation.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_reservation.this.project
}

output "this" {
  value = google_bigquery_reservation.this
}
```

[top](#index)