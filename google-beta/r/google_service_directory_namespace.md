# google_service_directory_namespace

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
module "google_service_directory_namespace" {
  source = "./modules/google-beta/r/google_service_directory_namespace"

  # labels - (optional) is a type of map of string
  labels = {}
  # location - (required) is a type of string
  location = null
  # namespace_id - (required) is a type of string
  namespace_id = null
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
variable "labels" {
  description = "(optional) - Resource labels associated with this Namespace. No more than 64 user\nlabels can be associated with a given resource. Label keys and values can\nbe no longer than 63 characters."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(required) - The location for the Namespace.\nA full list of valid locations can be found by running\n'gcloud beta service-directory locations list'."
  type        = string
}

variable "namespace_id" {
  description = "(required) - The Resource ID must be 1-63 characters long, including digits,\nlowercase letters or the hyphen character."
  type        = string
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
resource "google_service_directory_namespace" "this" {
  labels       = var.labels
  location     = var.location
  namespace_id = var.namespace_id
  project      = var.project

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
  value       = google_service_directory_namespace.this.id
}

output "name" {
  description = "returns a string"
  value       = google_service_directory_namespace.this.name
}

output "project" {
  description = "returns a string"
  value       = google_service_directory_namespace.this.project
}

output "this" {
  value = google_service_directory_namespace.this
}
```

[top](#index)