# google_storage_bucket_object_content

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
module "google_storage_bucket_object_content" {
  source = "./modules/google/d/google_storage_bucket_object_content"

  # bucket - (required) is a type of string
  bucket = null
  # content - (optional) is a type of string
  content = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required) - The name of the containing bucket."
  type        = string
}

variable "content" {
  description = "(optional) - Data as string to be uploaded. Must be defined if source is not. Note: The content field is marked as sensitive. To view the raw contents of the object, please define an output."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the object. If you're interpolating the name of this object, see output_name instead."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_storage_bucket_object_content" "this" {
  bucket  = var.bucket
  content = var.content
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cache_control" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.cache_control
}

output "content_disposition" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.content_disposition
}

output "content_encoding" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.content_encoding
}

output "content_language" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.content_language
}

output "content_type" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.content_type
}

output "crc32c" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.crc32c
}

output "detect_md5hash" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.detect_md5hash
}

output "id" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.id
}

output "kms_key_name" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.kms_key_name
}

output "md5hash" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.md5hash
}

output "media_link" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.media_link
}

output "metadata" {
  description = "returns a map of string"
  value       = data.google_storage_bucket_object_content.this.metadata
}

output "output_name" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.output_name
}

output "self_link" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.self_link
}

output "source" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.source
}

output "storage_class" {
  description = "returns a string"
  value       = data.google_storage_bucket_object_content.this.storage_class
}

output "this" {
  value = google_storage_bucket_object_content.this
}
```

[top](#index)