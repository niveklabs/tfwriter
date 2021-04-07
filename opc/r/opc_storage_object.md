# opc_storage_object

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_storage_object" {
  source = "./modules/opc/r/opc_storage_object"

  # container - (required) is a type of string
  container = null
  # content - (optional) is a type of string
  content = null
  # content_disposition - (optional) is a type of string
  content_disposition = null
  # content_encoding - (optional) is a type of string
  content_encoding = null
  # content_type - (optional) is a type of string
  content_type = null
  # copy_from - (optional) is a type of string
  copy_from = null
  # delete_at - (optional) is a type of number
  delete_at = null
  # etag - (optional) is a type of string
  etag = null
  # file - (optional) is a type of string
  file = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # transfer_encoding - (optional) is a type of string
  transfer_encoding = null
}
```

[top](#index)

### Variables

```terraform
variable "container" {
  description = "(required) - Name of the storage container"
  type        = string
}

variable "content" {
  description = "(optional) - Raw content in string-form of the data"
  type        = string
  default     = null
}

variable "content_disposition" {
  description = "(optional) - Overrides the behavior of the browser"
  type        = string
  default     = null
}

variable "content_encoding" {
  description = "(optional) - Set the content-encoding metadata"
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional) - Set the MIME type for the object"
  type        = string
  default     = null
}

variable "copy_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_at" {
  description = "(optional) - The date and time in UNIX Epoch time stamp format when the system removes the object"
  type        = number
  default     = null
}

variable "etag" {
  description = "(optional) - MD5 checksum value of the request body. Unquoted. Strongly Recommended"
  type        = string
  default     = null
}

variable "file" {
  description = "(optional) - File path for the content to use for data"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional) - The object metadata"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the storage object"
  type        = string
}

variable "transfer_encoding" {
  description = "(optional) - Sets the transfer encoding. Can only be 'chunked' or Nil, requires Content-Length to be 0 if set"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_storage_object" "this" {
  # container - (required) is a type of string
  container = var.container
  # content - (optional) is a type of string
  content = var.content
  # content_disposition - (optional) is a type of string
  content_disposition = var.content_disposition
  # content_encoding - (optional) is a type of string
  content_encoding = var.content_encoding
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # copy_from - (optional) is a type of string
  copy_from = var.copy_from
  # delete_at - (optional) is a type of number
  delete_at = var.delete_at
  # etag - (optional) is a type of string
  etag = var.etag
  # file - (optional) is a type of string
  file = var.file
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # transfer_encoding - (optional) is a type of string
  transfer_encoding = var.transfer_encoding
}
```

[top](#index)

### Outputs

```terraform
output "accept_ranges" {
  description = "returns a string"
  value       = opc_storage_object.this.accept_ranges
}

output "content_length" {
  description = "returns a number"
  value       = opc_storage_object.this.content_length
}

output "content_type" {
  description = "returns a string"
  value       = opc_storage_object.this.content_type
}

output "delete_at" {
  description = "returns a number"
  value       = opc_storage_object.this.delete_at
}

output "etag" {
  description = "returns a string"
  value       = opc_storage_object.this.etag
}

output "id" {
  description = "returns a string"
  value       = opc_storage_object.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = opc_storage_object.this.last_modified
}

output "metadata" {
  description = "returns a map of string"
  value       = opc_storage_object.this.metadata
}

output "object_manifest" {
  description = "returns a string"
  value       = opc_storage_object.this.object_manifest
}

output "timestamp" {
  description = "returns a string"
  value       = opc_storage_object.this.timestamp
}

output "transaction_id" {
  description = "returns a string"
  value       = opc_storage_object.this.transaction_id
}

output "this" {
  value = opc_storage_object.this
}
```

[top](#index)