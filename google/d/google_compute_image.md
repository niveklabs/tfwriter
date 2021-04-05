# google_compute_image

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
module "google_compute_image" {
  source = "./modules/google/d/google_compute_image"

  # family - (optional) is a type of string
  family = null
  # filter - (optional) is a type of string
  filter = null
  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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
data "google_compute_image" "this" {
  family  = var.family
  filter  = var.filter
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "archive_size_bytes" {
  description = "returns a number"
  value       = data.google_compute_image.this.archive_size_bytes
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_image.this.creation_timestamp
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_image.this.description
}

output "disk_size_gb" {
  description = "returns a number"
  value       = data.google_compute_image.this.disk_size_gb
}

output "family" {
  description = "returns a string"
  value       = data.google_compute_image.this.family
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_image.this.id
}

output "image_encryption_key_sha256" {
  description = "returns a string"
  value       = data.google_compute_image.this.image_encryption_key_sha256
}

output "image_id" {
  description = "returns a string"
  value       = data.google_compute_image.this.image_id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = data.google_compute_image.this.label_fingerprint
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_compute_image.this.labels
}

output "licenses" {
  description = "returns a list of string"
  value       = data.google_compute_image.this.licenses
}

output "name" {
  description = "returns a string"
  value       = data.google_compute_image.this.name
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_image.this.project
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_image.this.self_link
}

output "source_disk" {
  description = "returns a string"
  value       = data.google_compute_image.this.source_disk
}

output "source_disk_encryption_key_sha256" {
  description = "returns a string"
  value       = data.google_compute_image.this.source_disk_encryption_key_sha256
}

output "source_disk_id" {
  description = "returns a string"
  value       = data.google_compute_image.this.source_disk_id
}

output "source_image_id" {
  description = "returns a string"
  value       = data.google_compute_image.this.source_image_id
}

output "status" {
  description = "returns a string"
  value       = data.google_compute_image.this.status
}

output "this" {
  value = google_compute_image.this
}
```

[top](#index)