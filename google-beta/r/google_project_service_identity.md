# google_project_service_identity

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
module "google_project_service_identity" {
  source = "./modules/google-beta/r/google_project_service_identity"

  # project - (optional) is a type of string
  project = null
  # service - (required) is a type of string
  service = null

  timeouts = [{
    create = null
    delete = null
    read   = null
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

variable "service" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_project_service_identity" "this" {
  project = var.project
  service = var.service

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = google_project_service_identity.this.email
}

output "id" {
  description = "returns a string"
  value       = google_project_service_identity.this.id
}

output "project" {
  description = "returns a string"
  value       = google_project_service_identity.this.project
}

output "this" {
  value = google_project_service_identity.this
}
```

[top](#index)