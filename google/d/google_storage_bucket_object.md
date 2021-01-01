# google_storage_bucket_object

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
module "google_storage_bucket_object" {
  source = "./modules/google/d/google_storage_bucket_object"

  # bucket - (optional) is a type of string
  bucket = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "bucket" {
  description = "(optional) - The name of the containing bucket."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the object. If you're interpolating the name of this object, see output_name instead."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "google_storage_bucket_object" "this" {
  bucket = var.bucket
  name   = var.name
}
```

[top](#index)

### Outputs

```hcl
output "cache_control" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.cache_control
}

output "content" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.content
}

output "content_disposition" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.content_disposition
}

output "content_encoding" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.content_encoding
}

output "content_language" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.content_language
}

output "content_type" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.content_type
}

output "crc32c" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.crc32c
}

output "detect_md5hash" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.detect_md5hash
}

output "id" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.id
}

output "md5hash" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.md5hash
}

output "media_link" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.media_link
}

output "metadata" {
  description = "returns a map of string"
  value       = data.google_storage_bucket_object.this.metadata
}

output "output_name" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.output_name
}

output "self_link" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.self_link
}

output "source" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.source
}

output "storage_class" {
  description = "returns a string"
  value       = data.google_storage_bucket_object.this.storage_class
}

output "this" {
  value = google_storage_bucket_object.this
}
```

[top](#index)