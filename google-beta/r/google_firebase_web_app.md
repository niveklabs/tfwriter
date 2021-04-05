# google_firebase_web_app

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
module "google_firebase_web_app" {
  source = "./modules/google-beta/r/google_firebase_web_app"

  # display_name - (required) is a type of string
  display_name = null
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
variable "display_name" {
  description = "(required) - The user-assigned display name of the App."
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
resource "google_firebase_web_app" "this" {
  display_name = var.display_name
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
output "app_id" {
  description = "returns a string"
  value       = google_firebase_web_app.this.app_id
}

output "id" {
  description = "returns a string"
  value       = google_firebase_web_app.this.id
}

output "name" {
  description = "returns a string"
  value       = google_firebase_web_app.this.name
}

output "project" {
  description = "returns a string"
  value       = google_firebase_web_app.this.project
}

output "this" {
  value = google_firebase_web_app.this
}
```

[top](#index)