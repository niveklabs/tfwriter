# digitalocean_spaces_bucket_object

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_spaces_bucket_object" {
  source = "./modules/digitalocean/d/digitalocean_spaces_bucket_object"

  # bucket - (required) is a type of string
  bucket = null
  # key - (required) is a type of string
  key = null
  # range - (optional) is a type of string
  range = null
  # region - (required) is a type of string
  region = null
  # version_id - (optional) is a type of string
  version_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
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
data "digitalocean_spaces_bucket_object" "this" {
  bucket     = var.bucket
  key        = var.key
  range      = var.range
  region     = var.region
  version_id = var.version_id
}
```

[top](#index)

### Outputs

```terraform
output "body" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.body
}

output "cache_control" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.cache_control
}

output "content_disposition" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.content_disposition
}

output "content_encoding" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.content_encoding
}

output "content_language" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.content_language
}

output "content_length" {
  description = "returns a number"
  value       = data.digitalocean_spaces_bucket_object.this.content_length
}

output "content_type" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.etag
}

output "expiration" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.expiration
}

output "expires" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.expires
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.last_modified
}

output "metadata" {
  description = "returns a map of string"
  value       = data.digitalocean_spaces_bucket_object.this.metadata
}

output "version_id" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.version_id
}

output "website_redirect_location" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_object.this.website_redirect_location
}

output "this" {
  value = digitalocean_spaces_bucket_object.this
}
```

[top](#index)