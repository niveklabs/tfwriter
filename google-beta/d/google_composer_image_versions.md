# google_composer_image_versions

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_composer_image_versions" {
  source = "./modules/google-beta/d/google_composer_image_versions"

  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
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

```terraform
data "google_composer_image_versions" "this" {
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_composer_image_versions.this.id
}

output "image_versions" {
  description = "returns a list of object"
  value       = data.google_composer_image_versions.this.image_versions
}

output "project" {
  description = "returns a string"
  value       = data.google_composer_image_versions.this.project
}

output "region" {
  description = "returns a string"
  value       = data.google_composer_image_versions.this.region
}

output "this" {
  value = google_composer_image_versions.this
}
```

[top](#index)