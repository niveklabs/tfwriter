# google_compute_project_metadata_item

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_project_metadata_item" {
  source = "./modules/google/r/google_compute_project_metadata_item"

  # key - (required) is a type of string
  key = null
  # project - (optional) is a type of string
  project = null
  # value - (required) is a type of string
  value = null

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
variable "key" {
  description = "(required) - The metadata key to set."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "value" {
  description = "(required) - The value to set for the given metadata key."
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
resource "google_compute_project_metadata_item" "this" {
  key     = var.key
  project = var.project
  value   = var.value

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
  value       = google_compute_project_metadata_item.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_project_metadata_item.this.project
}

output "this" {
  value = google_compute_project_metadata_item.this
}
```

[top](#index)