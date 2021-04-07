# oci_objectstorage_object

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_object" {
  source = "./modules/oci/d/oci_objectstorage_object"

  # base64_encode_content - (optional) is a type of bool
  base64_encode_content = null
  # bucket - (required) is a type of string
  bucket = null
  # content_length_limit - (optional) is a type of number
  content_length_limit = null
  # http_response_cache_control - (optional) is a type of string
  http_response_cache_control = null
  # http_response_content_disposition - (optional) is a type of string
  http_response_content_disposition = null
  # http_response_content_encoding - (optional) is a type of string
  http_response_content_encoding = null
  # http_response_content_language - (optional) is a type of string
  http_response_content_language = null
  # http_response_content_type - (optional) is a type of string
  http_response_content_type = null
  # http_response_expires - (optional) is a type of string
  http_response_expires = null
  # namespace - (required) is a type of string
  namespace = null
  # object - (required) is a type of string
  object = null
  # version_id - (optional) is a type of string
  version_id = null
}
```

[top](#index)

### Variables

```terraform
variable "base64_encode_content" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bucket" {
  description = "(required)"
  type        = string
}

variable "content_length_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_response_cache_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_response_content_disposition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_response_content_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_response_content_language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_response_content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_response_expires" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "object" {
  description = "(required)"
  type        = string
}

variable "version_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_object" "this" {
  # base64_encode_content - (optional) is a type of bool
  base64_encode_content = var.base64_encode_content
  # bucket - (required) is a type of string
  bucket = var.bucket
  # content_length_limit - (optional) is a type of number
  content_length_limit = var.content_length_limit
  # http_response_cache_control - (optional) is a type of string
  http_response_cache_control = var.http_response_cache_control
  # http_response_content_disposition - (optional) is a type of string
  http_response_content_disposition = var.http_response_content_disposition
  # http_response_content_encoding - (optional) is a type of string
  http_response_content_encoding = var.http_response_content_encoding
  # http_response_content_language - (optional) is a type of string
  http_response_content_language = var.http_response_content_language
  # http_response_content_type - (optional) is a type of string
  http_response_content_type = var.http_response_content_type
  # http_response_expires - (optional) is a type of string
  http_response_expires = var.http_response_expires
  # namespace - (required) is a type of string
  namespace = var.namespace
  # object - (required) is a type of string
  object = var.object
  # version_id - (optional) is a type of string
  version_id = var.version_id
}
```

[top](#index)

### Outputs

```terraform
output "cache_control" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.cache_control
}

output "content" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content
}

output "content_disposition" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content_disposition
}

output "content_encoding" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content_encoding
}

output "content_language" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content_language
}

output "content_length" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content_length
}

output "content_md5" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content_md5
}

output "content_type" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.content_type
}

output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.oci_objectstorage_object.this.metadata
}

output "storage_tier" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.storage_tier
}

output "version_id" {
  description = "returns a string"
  value       = data.oci_objectstorage_object.this.version_id
}

output "this" {
  value = oci_objectstorage_object.this
}
```

[top](#index)