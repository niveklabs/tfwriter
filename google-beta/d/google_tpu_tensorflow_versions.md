# google_tpu_tensorflow_versions

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
module "google_tpu_tensorflow_versions" {
  source = "./modules/google-beta/d/google_tpu_tensorflow_versions"

  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null
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

variable "zone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_tpu_tensorflow_versions" "this" {
  project = var.project
  zone    = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_tpu_tensorflow_versions.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_tpu_tensorflow_versions.this.project
}

output "versions" {
  description = "returns a list of string"
  value       = data.google_tpu_tensorflow_versions.this.versions
}

output "zone" {
  description = "returns a string"
  value       = data.google_tpu_tensorflow_versions.this.zone
}

output "this" {
  value = google_tpu_tensorflow_versions.this
}
```

[top](#index)