# google_container_registry_repository

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
module "google_container_registry_repository" {
  source = "./modules/google/d/google_container_registry_repository"

  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```hcl
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "google_container_registry_repository" "this" {
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_container_registry_repository.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_container_registry_repository.this.project
}

output "repository_url" {
  description = "returns a string"
  value       = data.google_container_registry_repository.this.repository_url
}

output "this" {
  value = google_container_registry_repository.this
}
```

[top](#index)