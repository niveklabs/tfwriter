# google_game_services_realm

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_game_services_realm" {
  source = "./modules/google-beta/r/google_game_services_realm"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
  # realm_id - (required) is a type of string
  realm_id = null
  # time_zone - (required) is a type of string
  time_zone = null

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
variable "description" {
  description = "(optional) - Human readable description of the realm."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The labels associated with this realm. Each label is a key-value pair."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - Location of the Realm."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "realm_id" {
  description = "(required) - GCP region of the Realm."
  type        = string
}

variable "time_zone" {
  description = "(required) - Required. Time zone where all realm-specific policies are evaluated. The value of\nthis field must be from the IANA time zone database:\nhttps://www.iana.org/time-zones."
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
resource "google_game_services_realm" "this" {
  description = var.description
  labels      = var.labels
  location    = var.location
  project     = var.project
  realm_id    = var.realm_id
  time_zone   = var.time_zone

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
output "etag" {
  description = "returns a string"
  value       = google_game_services_realm.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_game_services_realm.this.id
}

output "name" {
  description = "returns a string"
  value       = google_game_services_realm.this.name
}

output "project" {
  description = "returns a string"
  value       = google_game_services_realm.this.project
}

output "this" {
  value = google_game_services_realm.this
}
```

[top](#index)