# google_container_registry

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_container_registry" {
  source = "./modules/google/r/google_container_registry"

  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
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

```hcl
resource "google_container_registry" "this" {
  location = var.location
  project  = var.project
}
```

[top](#index)

### Outputs

```hcl
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