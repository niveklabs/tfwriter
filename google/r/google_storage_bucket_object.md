# google_storage_bucket_object

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_storage_bucket_object" {
  source = null

  # bucket - (required) is a type of string
  bucket = null
  # cache_control - (optional) is a type of string
  cache_control = null
  # content - (optional) is a type of string
  content = null
  # content_disposition - (optional) is a type of string
  content_disposition = null
  # content_encoding - (optional) is a type of string
  content_encoding = null
  # content_language - (optional) is a type of string
  content_language = null
  # content_type - (optional) is a type of string
  content_type = null
  # detect_md5hash - (optional) is a type of string
  detect_md5hash = null
  # kms_key_name - (optional) is a type of string
  kms_key_name = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # source - (optional) is a type of string
  # storage_class - (optional) is a type of string
  storage_class = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required) - The name of the containing bucket."
  type        = string
}

variable "cache_control" {
  description = "(optional) - Cache-Control directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600"
  type        = string
  default     = null
}

variable "content" {
  description = "(optional) - Data as string to be uploaded. Must be defined if source is not. Note: The content field is marked as sensitive. To view the raw contents of the object, please define an output."
  type        = string
  default     = null
}

variable "content_disposition" {
  description = "(optional) - Content-Disposition of the object data."
  type        = string
  default     = null
}

variable "content_encoding" {
  description = "(optional) - Content-Encoding of the object data."
  type        = string
  default     = null
}

variable "content_language" {
  description = "(optional) - Content-Language of the object data."
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional) - Content-Type of the object data. Defaults to \"application/octet-stream\" or \"text/plain; charset=utf-8\"."
  type        = string
  default     = null
}

variable "detect_md5hash" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_name" {
  description = "(optional) - Resource name of the Cloud KMS key that will be used to encrypt the object. Overrides the object metadata's kmsKeyName value, if any."
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional) - User-provided metadata, in key/value pairs."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The name of the object. If you're interpolating the name of this object, see output_name instead."
  type        = string
}

variable "source" {
  description = "(optional) - A path to the data you want to upload. Must be defined if content is not."
  type        = string
  default     = null
}

variable "storage_class" {
  description = "(optional) - The StorageClass of the new bucket object. Supported values include: MULTI_REGIONAL, REGIONAL, NEARLINE, COLDLINE, ARCHIVE. If not provided, this defaults to the bucket's default storage class or to a standard class."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_storage_bucket_object" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # cache_control - (optional) is a type of string
  cache_control = var.cache_control
  # content - (optional) is a type of string
  content = var.content
  # content_disposition - (optional) is a type of string
  content_disposition = var.content_disposition
  # content_encoding - (optional) is a type of string
  content_encoding = var.content_encoding
  # content_language - (optional) is a type of string
  content_language = var.content_language
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # detect_md5hash - (optional) is a type of string
  detect_md5hash = var.detect_md5hash
  # kms_key_name - (optional) is a type of string
  kms_key_name = var.kms_key_name
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # source - (optional) is a type of string
  source = var.source
  # storage_class - (optional) is a type of string
  storage_class = var.storage_class
}
```

[top](#index)

### Outputs

```terraform
output "content_type" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.content_type
}

output "crc32c" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.crc32c
}

output "id" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.id
}

output "kms_key_name" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.kms_key_name
}

output "md5hash" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.md5hash
}

output "media_link" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.media_link
}

output "output_name" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.output_name
}

output "self_link" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.self_link
}

output "storage_class" {
  description = "returns a string"
  value       = google_storage_bucket_object.this.storage_class
}

output "this" {
  value = google_storage_bucket_object.this
}
```

[top](#index)