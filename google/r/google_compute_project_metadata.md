# google_compute_project_metadata

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_project_metadata" {
  source = "./modules/google/r/google_compute_project_metadata"

  # metadata - (required) is a type of map of string
  metadata = {}
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
variable "metadata" {
  description = "(required) - A series of key value pairs."
  type        = map(string)
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
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
resource "google_compute_project_metadata" "this" {
  # metadata - (required) is a type of map of string
  metadata = var.metadata
  # project - (optional) is a type of string
  project = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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
  value       = google_compute_project_metadata.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_project_metadata.this.project
}

output "this" {
  value = google_compute_project_metadata.this
}
```

[top](#index)