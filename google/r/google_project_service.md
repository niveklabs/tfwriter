# google_project_service

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_project_service" {
  source = "./modules/google/r/google_project_service"

  # disable_dependent_services - (optional) is a type of bool
  disable_dependent_services = null
  # disable_on_destroy - (optional) is a type of bool
  disable_on_destroy = null
  # project - (optional) is a type of string
  project = null
  # service - (required) is a type of string
  service = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "disable_dependent_services" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

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
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_project_service" "this" {
  disable_dependent_services = var.disable_dependent_services
  disable_on_destroy         = var.disable_on_destroy
  project                    = var.project
  service                    = var.service

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_project_service.this.id
}

output "project" {
  description = "returns a string"
  value       = google_project_service.this.project
}

output "this" {
  value = google_project_service.this
}
```

[top](#index)