# tencentcloud_cos_bucket_object

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cos_bucket_object" {
  source = null

  # acl - (optional) is a type of string
  acl = null
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
  # content_type - (optional) is a type of string
  content_type = null
  # etag - (optional) is a type of string
  etag = null
  # key - (required) is a type of string
  key = null
  # source - (optional) is a type of string
  # storage_class - (optional) is a type of string
  storage_class = null
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional) - The canned ACL to apply. Available values include `private`, `public-read`, and `public-read-write`. Defaults to `private`."
  type        = string
  default     = null
}

variable "bucket" {
  description = "(required) - The name of a bucket to use. Bucket format should be [custom name]-[appid], for example `mycos-1258798060`."
  type        = string
}

variable "cache_control" {
  description = "(optional) - Specifies caching behavior along the request/reply chain. For further details, RFC2616 can be referred."
  type        = string
  default     = null
}

variable "content" {
  description = "(optional) - Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text."
  type        = string
  default     = null
}

variable "content_disposition" {
  description = "(optional) - Specifies presentational information for the object."
  type        = string
  default     = null
}

variable "content_encoding" {
  description = "(optional) - Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field."
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional) - A standard MIME type describing the format of the object data."
  type        = string
  default     = null
}

variable "etag" {
  description = "(optional) - The ETag generated for the object (an MD5 sum of the object content)."
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - The name of the object once it is in the bucket."
  type        = string
}

variable "source" {
  description = "(optional) - The path to the source file being uploaded to the bucket."
  type        = string
  default     = null
}

variable "storage_class" {
  description = "(optional) - Object storage type, Available values include `STANDARD`, `STANDARD_IA` and `ARCHIVE`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cos_bucket_object" "this" {
  # acl - (optional) is a type of string
  acl = var.acl
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
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # etag - (optional) is a type of string
  etag = var.etag
  # key - (required) is a type of string
  key = var.key
  # source - (optional) is a type of string
  source = var.source
  # storage_class - (optional) is a type of string
  storage_class = var.storage_class
}
```

[top](#index)

### Outputs

```terraform
output "cache_control" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket_object.this.cache_control
}

output "content_type" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket_object.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket_object.this.etag
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket_object.this.id
}

output "storage_class" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket_object.this.storage_class
}

output "this" {
  value = tencentcloud_cos_bucket_object.this
}
```

[top](#index)