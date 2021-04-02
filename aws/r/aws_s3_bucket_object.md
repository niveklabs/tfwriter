# aws_s3_bucket_object

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3_bucket_object" {
  source = null

  # acl - (optional) is a type of string
  acl = null
  # bucket - (required) is a type of string
  bucket = null
  # cache_control - (optional) is a type of string
  cache_control = null
  # content - (optional) is a type of string
  content = null
  # content_base64 - (optional) is a type of string
  content_base64 = null
  # content_disposition - (optional) is a type of string
  content_disposition = null
  # content_encoding - (optional) is a type of string
  content_encoding = null
  # content_language - (optional) is a type of string
  content_language = null
  # content_type - (optional) is a type of string
  content_type = null
  # etag - (optional) is a type of string
  etag = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # key - (required) is a type of string
  key = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # object_lock_legal_hold_status - (optional) is a type of string
  object_lock_legal_hold_status = null
  # object_lock_mode - (optional) is a type of string
  object_lock_mode = null
  # object_lock_retain_until_date - (optional) is a type of string
  object_lock_retain_until_date = null
  # server_side_encryption - (optional) is a type of string
  server_side_encryption = null
  # source - (optional) is a type of string
  # storage_class - (optional) is a type of string
  storage_class = null
  # tags - (optional) is a type of map of string
  tags = {}
  # website_redirect - (optional) is a type of string
  website_redirect = null
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bucket" {
  description = "(required)"
  type        = string
}

variable "cache_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_base64" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_disposition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "etag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "object_lock_legal_hold_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_lock_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_lock_retain_until_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_side_encryption" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "website_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_object" "this" {
  acl                           = var.acl
  bucket                        = var.bucket
  cache_control                 = var.cache_control
  content                       = var.content
  content_base64                = var.content_base64
  content_disposition           = var.content_disposition
  content_encoding              = var.content_encoding
  content_language              = var.content_language
  content_type                  = var.content_type
  etag                          = var.etag
  force_destroy                 = var.force_destroy
  key                           = var.key
  kms_key_id                    = var.kms_key_id
  metadata                      = var.metadata
  object_lock_legal_hold_status = var.object_lock_legal_hold_status
  object_lock_mode              = var.object_lock_mode
  object_lock_retain_until_date = var.object_lock_retain_until_date
  server_side_encryption        = var.server_side_encryption
  source                        = var.source
  storage_class                 = var.storage_class
  tags                          = var.tags
  website_redirect              = var.website_redirect
}
```

[top](#index)

### Outputs

```terraform
output "content_type" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.etag
}

output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.kms_key_id
}

output "server_side_encryption" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.server_side_encryption
}

output "storage_class" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.storage_class
}

output "version_id" {
  description = "returns a string"
  value       = aws_s3_bucket_object.this.version_id
}

output "this" {
  value = aws_s3_bucket_object.this
}
```

[top](#index)