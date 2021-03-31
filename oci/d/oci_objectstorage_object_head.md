# oci_objectstorage_object_head

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_object_head" {
  source = "./modules/oci/d/oci_objectstorage_object_head"

  # bucket - (required) is a type of string
  bucket = null
  # namespace - (required) is a type of string
  namespace = null
  # object - (required) is a type of string
  object = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "object" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_object_head" "this" {
  bucket    = var.bucket
  namespace = var.namespace
  object    = var.object
}
```

[top](#index)

### Outputs

```terraform
output "archival_state" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_head.this.archival_state
}

output "content_length" {
  description = "returns a number"
  value       = data.oci_objectstorage_object_head.this.content_length
}

output "content_type" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_head.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_head.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_head.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.oci_objectstorage_object_head.this.metadata
}

output "storage_tier" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_head.this.storage_tier
}

output "this" {
  value = oci_objectstorage_object_head.this
}
```

[top](#index)