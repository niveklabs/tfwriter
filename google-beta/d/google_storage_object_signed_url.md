# google_storage_object_signed_url

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_storage_object_signed_url" {
  source = "./modules/google-beta/d/google_storage_object_signed_url"

  # bucket - (required) is a type of string
  bucket = null
  # content_md5 - (optional) is a type of string
  content_md5 = null
  # content_type - (optional) is a type of string
  content_type = null
  # credentials - (optional) is a type of string
  credentials = null
  # duration - (optional) is a type of string
  duration = null
  # extension_headers - (optional) is a type of map of string
  extension_headers = {}
  # http_method - (optional) is a type of string
  http_method = null
  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
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

variable "credentials" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extension_headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "http_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_storage_object_signed_url" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # content_md5 - (optional) is a type of string
  content_md5 = var.content_md5
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # credentials - (optional) is a type of string
  credentials = var.credentials
  # duration - (optional) is a type of string
  duration = var.duration
  # extension_headers - (optional) is a type of map of string
  extension_headers = var.extension_headers
  # http_method - (optional) is a type of string
  http_method = var.http_method
  # path - (required) is a type of string
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_storage_object_signed_url.this.id
}

output "signed_url" {
  description = "returns a string"
  value       = data.google_storage_object_signed_url.this.signed_url
}

output "this" {
  value = google_storage_object_signed_url.this
}
```

[top](#index)