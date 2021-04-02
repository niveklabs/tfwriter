# oci_objectstorage_object

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_object" {
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
  # content_md5 - (optional) is a type of string
  content_md5 = null
  # content_type - (optional) is a type of string
  content_type = null
  # delete_all_object_versions - (optional) is a type of bool
  delete_all_object_versions = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # namespace - (required) is a type of string
  namespace = null
  # object - (required) is a type of string
  object = null
  # source - (optional) is a type of string
  # storage_tier - (optional) is a type of string
  storage_tier = null

  source_uri_details = [{
    bucket                                = null
    destination_object_if_match_etag      = null
    destination_object_if_none_match_etag = null
    namespace                             = null
    object                                = null
    region                                = null
    source_object_if_match_etag           = null
    source_version_id                     = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "content_language" {
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

variable "delete_all_object_versions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
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

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_uri_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket                                = string
      destination_object_if_match_etag      = string
      destination_object_if_none_match_etag = string
      namespace                             = string
      object                                = string
      region                                = string
      source_object_if_match_etag           = string
      source_version_id                     = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_objectstorage_object" "this" {
  bucket                     = var.bucket
  cache_control              = var.cache_control
  content                    = var.content
  content_disposition        = var.content_disposition
  content_encoding           = var.content_encoding
  content_language           = var.content_language
  content_md5                = var.content_md5
  content_type               = var.content_type
  delete_all_object_versions = var.delete_all_object_versions
  metadata                   = var.metadata
  namespace                  = var.namespace
  object                     = var.object
  source                     = var.source
  storage_tier               = var.storage_tier

  dynamic "source_uri_details" {
    for_each = var.source_uri_details
    content {
      bucket                                = source_uri_details.value["bucket"]
      destination_object_if_match_etag      = source_uri_details.value["destination_object_if_match_etag"]
      destination_object_if_none_match_etag = source_uri_details.value["destination_object_if_none_match_etag"]
      namespace                             = source_uri_details.value["namespace"]
      object                                = source_uri_details.value["object"]
      region                                = source_uri_details.value["region"]
      source_object_if_match_etag           = source_uri_details.value["source_object_if_match_etag"]
      source_version_id                     = source_uri_details.value["source_version_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "content_length" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.content_length
}

output "content_md5" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.content_md5
}

output "content_type" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.content_type
}

output "id" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.state
}

output "storage_tier" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.storage_tier
}

output "version_id" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.version_id
}

output "work_request_id" {
  description = "returns a string"
  value       = oci_objectstorage_object.this.work_request_id
}

output "this" {
  value = oci_objectstorage_object.this
}
```

[top](#index)