# linode_object_storage_object

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_object_storage_object" {
  source = null

  # access_key - (required) is a type of string
  access_key = null
  # acl - (optional) is a type of string
  acl = null
  # bucket - (required) is a type of string
  bucket = null
  # cache_control - (optional) is a type of string
  cache_control = null
  # cluster - (required) is a type of string
  cluster = null
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
  # metadata - (optional) is a type of map of string
  metadata = {}
  # secret_key - (required) is a type of string
  secret_key = null
  # source - (optional) is a type of string
  # website_redirect - (optional) is a type of string
  website_redirect = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key" {
  description = "(required)"
  type        = string
}

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

variable "cluster" {
  description = "(required)"
  type        = string
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

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "secret_key" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "(optional)"
  type        = string
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
resource "linode_object_storage_object" "this" {
  # access_key - (required) is a type of string
  access_key = var.access_key
  # acl - (optional) is a type of string
  acl = var.acl
  # bucket - (required) is a type of string
  bucket = var.bucket
  # cache_control - (optional) is a type of string
  cache_control = var.cache_control
  # cluster - (required) is a type of string
  cluster = var.cluster
  # content - (optional) is a type of string
  content = var.content
  # content_base64 - (optional) is a type of string
  content_base64 = var.content_base64
  # content_disposition - (optional) is a type of string
  content_disposition = var.content_disposition
  # content_encoding - (optional) is a type of string
  content_encoding = var.content_encoding
  # content_language - (optional) is a type of string
  content_language = var.content_language
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # etag - (optional) is a type of string
  etag = var.etag
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # key - (required) is a type of string
  key = var.key
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # secret_key - (required) is a type of string
  secret_key = var.secret_key
  # source - (optional) is a type of string
  source = var.source
  # website_redirect - (optional) is a type of string
  website_redirect = var.website_redirect
}
```

[top](#index)

### Outputs

```terraform
output "content_type" {
  description = "returns a string"
  value       = linode_object_storage_object.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = linode_object_storage_object.this.etag
}

output "id" {
  description = "returns a string"
  value       = linode_object_storage_object.this.id
}

output "version_id" {
  description = "returns a string"
  value       = linode_object_storage_object.this.version_id
}

output "this" {
  value = linode_object_storage_object.this
}
```

[top](#index)