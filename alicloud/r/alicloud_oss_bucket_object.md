# alicloud_oss_bucket_object

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_oss_bucket_object" {
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
  # content_md5 - (optional) is a type of string
  content_md5 = null
  # content_type - (optional) is a type of string
  content_type = null
  # expires - (optional) is a type of string
  expires = null
  # key - (required) is a type of string
  key = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # server_side_encryption - (optional) is a type of string
  server_side_encryption = null
  # source - (optional) is a type of string
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

variable "content_md5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expires" {
  description = "(optional)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "alicloud_oss_bucket_object" "this" {
  acl                    = var.acl
  bucket                 = var.bucket
  cache_control          = var.cache_control
  content                = var.content
  content_disposition    = var.content_disposition
  content_encoding       = var.content_encoding
  content_md5            = var.content_md5
  content_type           = var.content_type
  expires                = var.expires
  key                    = var.key
  kms_key_id             = var.kms_key_id
  server_side_encryption = var.server_side_encryption
  source                 = var.source
}
```

[top](#index)

### Outputs

```terraform
output "content_length" {
  description = "returns a string"
  value       = alicloud_oss_bucket_object.this.content_length
}

output "content_type" {
  description = "returns a string"
  value       = alicloud_oss_bucket_object.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = alicloud_oss_bucket_object.this.etag
}

output "id" {
  description = "returns a string"
  value       = alicloud_oss_bucket_object.this.id
}

output "version_id" {
  description = "returns a string"
  value       = alicloud_oss_bucket_object.this.version_id
}

output "this" {
  value = alicloud_oss_bucket_object.this
}
```

[top](#index)