# google_service_directory_service

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
module "google_service_directory_service" {
  source = "./modules/google-beta/r/google_service_directory_service"

  # metadata - (optional) is a type of map of string
  metadata = {}
  # namespace - (required) is a type of string
  namespace = null
  # service_id - (required) is a type of string
  service_id = null

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
variable "metadata" {
  description = "(optional) - Metadata for the service. This data can be consumed\nby service clients. The entire metadata dictionary may contain\nup to 2000 characters, spread across all key-value pairs.\nMetadata that goes beyond any these limits will be rejected."
  type        = map(string)
  default     = null
}

variable "namespace" {
  description = "(required) - The resource name of the namespace this service will belong to."
  type        = string
}

variable "service_id" {
  description = "(required) - The Resource ID must be 1-63 characters long, including digits,\nlowercase letters or the hyphen character."
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
resource "google_service_directory_service" "this" {
  metadata   = var.metadata
  namespace  = var.namespace
  service_id = var.service_id

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
  value       = google_service_directory_service.this.id
}

output "name" {
  description = "returns a string"
  value       = google_service_directory_service.this.name
}

output "this" {
  value = google_service_directory_service.this
}
```

[top](#index)