# google_compute_backend_bucket

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
module "google_compute_backend_bucket" {
  source = "./modules/google/d/google_compute_backend_bucket"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the\nlast character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_backend_bucket" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "bucket_name" {
  description = "returns a string"
  value       = data.google_compute_backend_bucket.this.bucket_name
}

output "cdn_policy" {
  description = "returns a list of object"
  value       = data.google_compute_backend_bucket.this.cdn_policy
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_backend_bucket.this.creation_timestamp
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_backend_bucket.this.description
}

output "enable_cdn" {
  description = "returns a bool"
  value       = data.google_compute_backend_bucket.this.enable_cdn
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_backend_bucket.this.id
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_backend_bucket.this.self_link
}

output "this" {
  value = google_compute_backend_bucket.this
}
```

[top](#index)