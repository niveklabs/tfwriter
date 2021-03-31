# google_compute_backend_service_signed_url_key

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
module "google_compute_backend_service_signed_url_key" {
  source = "./modules/google-beta/r/google_compute_backend_service_signed_url_key"

  # backend_service - (required) is a type of string
  backend_service = null
  # key_value - (required) is a type of string
  key_value = null
  # name - (required) is a type of string
  name = null
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
variable "backend_service" {
  description = "(required) - The backend service this signed URL key belongs."
  type        = string
}

variable "key_value" {
  description = "(required) - 128-bit key value used for signing the URL. The key value must be a\nvalid RFC 4648 Section 5 base64url encoded string."
  type        = string
}

variable "name" {
  description = "(required) - Name of the signed URL key."
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
resource "google_compute_backend_service_signed_url_key" "this" {
  backend_service = var.backend_service
  key_value       = var.key_value
  name            = var.name
  project         = var.project

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
  value       = google_compute_backend_service_signed_url_key.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_backend_service_signed_url_key.this.project
}

output "this" {
  value = google_compute_backend_service_signed_url_key.this
}
```

[top](#index)