# google_notebooks_location

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
module "google_notebooks_location" {
  source = "./modules/google/r/google_notebooks_location"

  # name - (optional) is a type of string
  name = null
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
variable "name" {
  description = "(optional) - Name of the Location resource."
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
resource "google_notebooks_location" "this" {
  name    = var.name
  project = var.project

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
  value       = google_notebooks_location.this.id
}

output "project" {
  description = "returns a string"
  value       = google_notebooks_location.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_notebooks_location.this.self_link
}

output "this" {
  value = google_notebooks_location.this
}
```

[top](#index)