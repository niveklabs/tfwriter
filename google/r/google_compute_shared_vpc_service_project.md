# google_compute_shared_vpc_service_project

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_shared_vpc_service_project" {
  source = "./modules/google/r/google_compute_shared_vpc_service_project"

  # host_project - (required) is a type of string
  host_project = null
  # service_project - (required) is a type of string
  service_project = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "host_project" {
  description = "(required) - The ID of a host project to associate."
  type        = string
}

variable "service_project" {
  description = "(required) - The ID of the project that will serve as a Shared VPC service project."
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
resource "google_compute_shared_vpc_service_project" "this" {
  host_project    = var.host_project
  service_project = var.service_project

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
  value       = google_compute_shared_vpc_service_project.this.id
}

output "this" {
  value = google_compute_shared_vpc_service_project.this
}
```

[top](#index)