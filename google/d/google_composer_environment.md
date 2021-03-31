# google_composer_environment

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_composer_environment" {
  source = "./modules/google/d/google_composer_environment"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the environment."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The location or Compute Engine region for the environment."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_composer_environment" "this" {
  name    = var.name
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "config" {
  description = "returns a list of object"
  value       = data.google_composer_environment.this.config
}

output "id" {
  description = "returns a string"
  value       = data.google_composer_environment.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_composer_environment.this.labels
}

output "this" {
  value = google_composer_environment.this
}
```

[top](#index)