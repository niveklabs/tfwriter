# google_firebase_project

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
module "google_firebase_project" {
  source = "./modules/google-beta/r/google_firebase_project"

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
resource "google_firebase_project" "this" {
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
output "display_name" {
  description = "returns a string"
  value       = google_firebase_project.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_firebase_project.this.id
}

output "project" {
  description = "returns a string"
  value       = google_firebase_project.this.project
}

output "project_number" {
  description = "returns a string"
  value       = google_firebase_project.this.project_number
}

output "this" {
  value = google_firebase_project.this
}
```

[top](#index)