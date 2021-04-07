# aws_s3_object_copy

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
module "aws_s3_object_copy" {
  source = null

  # acl - (optional) is a type of string
  acl = null
  # bucket - (required) is a type of string
  bucket = null
  # cache_control - (optional) is a type of string
  cache_control = null
  # content_disposition - (optional) is a type of string
  content_disposition = null
  # content_encoding - (optional) is a type of string
  content_encoding = null
  # content_language - (optional) is a type of string
  content_language = null
  # content_type - (optional) is a type of string
  content_type = null
  # copy_if_match - (optional) is a type of string
  copy_if_match = null
  # copy_if_modified_since - (optional) is a type of string
  copy_if_modified_since = null
  # copy_if_none_match - (optional) is a type of string
  copy_if_none_match = null
  # copy_if_unmodified_since - (optional) is a type of string
  copy_if_unmodified_since = null
  # customer_algorithm - (optional) is a type of string
  customer_algorithm = null
  # customer_key - (optional) is a type of string
  customer_key = null
  # customer_key_md5 - (optional) is a type of string
  customer_key_md5 = null
  # expected_bucket_owner - (optional) is a type of string
  expected_bucket_owner = null
  # expected_source_bucket_owner - (optional) is a type of string
  expected_source_bucket_owner = null
  # expires - (optional) is a type of string
  expires = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # key - (required) is a type of string
  key = null
  # kms_encryption_context - (optional) is a type of string
  kms_encryption_context = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # metadata_directive - (optional) is a type of string
  metadata_directive = null
  # object_lock_legal_hold_status - (optional) is a type of string
  object_lock_legal_hold_status = null
  # object_lock_mode - (optional) is a type of string
  object_lock_mode = null
  # object_lock_retain_until_date - (optional) is a type of string
  object_lock_retain_until_date = null
  # request_payer - (optional) is a type of string
  request_payer = null
  # server_side_encryption - (optional) is a type of string
  server_side_encryption = null
  # source - (required) is a type of string
  # source_customer_algorithm - (optional) is a type of string
  source_customer_algorithm = null
  # source_customer_key - (optional) is a type of string
  source_customer_key = null
  # source_customer_key_md5 - (optional) is a type of string
  source_customer_key_md5 = null
  # storage_class - (optional) is a type of string
  storage_class = null
  # tagging_directive - (optional) is a type of string
  tagging_directive = null
  # tags - (optional) is a type of map of string
  tags = {}
  # website_redirect - (optional) is a type of string
  website_redirect = null

  grant = [{
    email       = null
    id          = null
    permissions = []
    type        = null
    uri         = null
  }]
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

variable "copy_if_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "copy_if_modified_since" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "copy_if_none_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "copy_if_unmodified_since" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customer_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customer_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customer_key_md5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expected_bucket_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expected_source_bucket_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expires" {
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

variable "kms_encryption_context" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "metadata_directive" {
  description = "(optional)"
  type        = string
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

variable "request_payer" {
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
  description = "(required)"
  type        = string
}

variable "source_customer_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_customer_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_customer_key_md5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tagging_directive" {
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

variable "grant" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      email       = string
      id          = string
      permissions = set(string)
      type        = string
      uri         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_object_copy" "this" {
  # acl - (optional) is a type of string
  acl = var.acl
  # bucket - (required) is a type of string
  bucket = var.bucket
  # cache_control - (optional) is a type of string
  cache_control = var.cache_control
  # content_disposition - (optional) is a type of string
  content_disposition = var.content_disposition
  # content_encoding - (optional) is a type of string
  content_encoding = var.content_encoding
  # content_language - (optional) is a type of string
  content_language = var.content_language
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # copy_if_match - (optional) is a type of string
  copy_if_match = var.copy_if_match
  # copy_if_modified_since - (optional) is a type of string
  copy_if_modified_since = var.copy_if_modified_since
  # copy_if_none_match - (optional) is a type of string
  copy_if_none_match = var.copy_if_none_match
  # copy_if_unmodified_since - (optional) is a type of string
  copy_if_unmodified_since = var.copy_if_unmodified_since
  # customer_algorithm - (optional) is a type of string
  customer_algorithm = var.customer_algorithm
  # customer_key - (optional) is a type of string
  customer_key = var.customer_key
  # customer_key_md5 - (optional) is a type of string
  customer_key_md5 = var.customer_key_md5
  # expected_bucket_owner - (optional) is a type of string
  expected_bucket_owner = var.expected_bucket_owner
  # expected_source_bucket_owner - (optional) is a type of string
  expected_source_bucket_owner = var.expected_source_bucket_owner
  # expires - (optional) is a type of string
  expires = var.expires
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # key - (required) is a type of string
  key = var.key
  # kms_encryption_context - (optional) is a type of string
  kms_encryption_context = var.kms_encryption_context
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # metadata_directive - (optional) is a type of string
  metadata_directive = var.metadata_directive
  # object_lock_legal_hold_status - (optional) is a type of string
  object_lock_legal_hold_status = var.object_lock_legal_hold_status
  # object_lock_mode - (optional) is a type of string
  object_lock_mode = var.object_lock_mode
  # object_lock_retain_until_date - (optional) is a type of string
  object_lock_retain_until_date = var.object_lock_retain_until_date
  # request_payer - (optional) is a type of string
  request_payer = var.request_payer
  # server_side_encryption - (optional) is a type of string
  server_side_encryption = var.server_side_encryption
  # source - (required) is a type of string
  source = var.source
  # source_customer_algorithm - (optional) is a type of string
  source_customer_algorithm = var.source_customer_algorithm
  # source_customer_key - (optional) is a type of string
  source_customer_key = var.source_customer_key
  # source_customer_key_md5 - (optional) is a type of string
  source_customer_key_md5 = var.source_customer_key_md5
  # storage_class - (optional) is a type of string
  storage_class = var.storage_class
  # tagging_directive - (optional) is a type of string
  tagging_directive = var.tagging_directive
  # tags - (optional) is a type of map of string
  tags = var.tags
  # website_redirect - (optional) is a type of string
  website_redirect = var.website_redirect

  dynamic "grant" {
    for_each = var.grant
    content {
      # email - (optional) is a type of string
      email = grant.value["email"]
      # id - (optional) is a type of string
      id = grant.value["id"]
      # permissions - (required) is a type of set of string
      permissions = grant.value["permissions"]
      # type - (required) is a type of string
      type = grant.value["type"]
      # uri - (optional) is a type of string
      uri = grant.value["uri"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cache_control" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.cache_control
}

output "content_disposition" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.content_disposition
}

output "content_encoding" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.content_encoding
}

output "content_language" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.content_language
}

output "content_type" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.content_type
}

output "customer_algorithm" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.customer_algorithm
}

output "customer_key_md5" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.customer_key_md5
}

output "etag" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.etag
}

output "expiration" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.expiration
}

output "id" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.id
}

output "kms_encryption_context" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.kms_encryption_context
  sensitive   = true
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.kms_key_id
  sensitive   = true
}

output "last_modified" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.last_modified
}

output "metadata" {
  description = "returns a map of string"
  value       = aws_s3_object_copy.this.metadata
}

output "object_lock_legal_hold_status" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.object_lock_legal_hold_status
}

output "object_lock_mode" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.object_lock_mode
}

output "object_lock_retain_until_date" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.object_lock_retain_until_date
}

output "request_charged" {
  description = "returns a bool"
  value       = aws_s3_object_copy.this.request_charged
}

output "server_side_encryption" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.server_side_encryption
}

output "source_version_id" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.source_version_id
}

output "storage_class" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.storage_class
}

output "version_id" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.version_id
}

output "website_redirect" {
  description = "returns a string"
  value       = aws_s3_object_copy.this.website_redirect
}

output "this" {
  value = aws_s3_object_copy.this
}
```

[top](#index)