# google_firebase_project_location

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
module "google_firebase_project_location" {
  source = "./modules/google-beta/r/google_firebase_project_location"

  # location_id - (required) is a type of string
  location_id = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location_id" {
  description = "(required) - The ID of the default GCP resource location for the Project. The location must be one of the available GCP\nresource locations."
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_firebase_project_location" "this" {
  location_id = var.location_id
  project     = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_firebase_project_location.this.id
}

output "project" {
  description = "returns a string"
  value       = google_firebase_project_location.this.project
}

output "this" {
  value = google_firebase_project_location.this
}
```

[top](#index)