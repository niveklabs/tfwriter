# google_container_registry

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
module "google_container_registry" {
  source = "./modules/google-beta/r/google_container_registry"

  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(optional) - The location of the registry. One of ASIA, EU, US or not specified. See the official documentation for more information on registry locations."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_container_registry" "this" {
  # location - (optional) is a type of string
  location = var.location
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "bucket_self_link" {
  description = "returns a string"
  value       = google_container_registry.this.bucket_self_link
}

output "id" {
  description = "returns a string"
  value       = google_container_registry.this.id
}

output "project" {
  description = "returns a string"
  value       = google_container_registry.this.project
}

output "this" {
  value = google_container_registry.this
}
```

[top](#index)