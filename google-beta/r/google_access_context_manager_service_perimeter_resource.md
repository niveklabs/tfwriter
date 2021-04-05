# google_access_context_manager_service_perimeter_resource

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
module "google_access_context_manager_service_perimeter_resource" {
  source = "./modules/google-beta/r/google_access_context_manager_service_perimeter_resource"

  # perimeter_name - (required) is a type of string
  perimeter_name = null
  # resource - (required) is a type of string
  resource = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "perimeter_name" {
  description = "(required) - The name of the Service Perimeter to add this resource to."
  type        = string
}

variable "resource" {
  description = "(required) - A GCP resource that is inside of the service perimeter.\nCurrently only projects are allowed.\nFormat: projects/{project_number}"
  type        = string
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
resource "google_access_context_manager_service_perimeter_resource" "this" {
  perimeter_name = var.perimeter_name
  resource       = var.resource

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
  value       = google_access_context_manager_service_perimeter_resource.this.id
}

output "this" {
  value = google_access_context_manager_service_perimeter_resource.this
}
```

[top](#index)