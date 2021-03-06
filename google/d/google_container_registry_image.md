# google_container_registry_image

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_container_registry_image" {
  source = "./modules/google/d/google_container_registry_image"

  # digest - (optional) is a type of string
  digest = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # tag - (optional) is a type of string
  tag = null
}
```

[top](#index)

### Variables

```terraform
variable "digest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

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

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_container_registry_image" "this" {
  # digest - (optional) is a type of string
  digest = var.digest
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # tag - (optional) is a type of string
  tag = var.tag
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_container_registry_image.this.id
}

output "image_url" {
  description = "returns a string"
  value       = data.google_container_registry_image.this.image_url
}

output "project" {
  description = "returns a string"
  value       = data.google_container_registry_image.this.project
}

output "this" {
  value = google_container_registry_image.this
}
```

[top](#index)