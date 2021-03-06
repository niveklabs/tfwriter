# oci_objectstorage_preauthrequest

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_preauthrequest" {
  source = "./modules/oci/r/oci_objectstorage_preauthrequest"

  # access_type - (required) is a type of string
  access_type = null
  # bucket - (required) is a type of string
  bucket = null
  # bucket_listing_action - (optional) is a type of string
  bucket_listing_action = null
  # name - (required) is a type of string
  name = null
  # namespace - (required) is a type of string
  namespace = null
  # object - (optional) is a type of string
  object = null
  # time_expires - (required) is a type of string
  time_expires = null

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
variable "access_type" {
  description = "(required)"
  type        = string
}

variable "bucket" {
  description = "(required)"
  type        = string
}

variable "bucket_listing_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "object" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_expires" {
  description = "(required)"
  type        = string
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
resource "oci_objectstorage_preauthrequest" "this" {
  # access_type - (required) is a type of string
  access_type = var.access_type
  # bucket - (required) is a type of string
  bucket = var.bucket
  # bucket_listing_action - (optional) is a type of string
  bucket_listing_action = var.bucket_listing_action
  # name - (required) is a type of string
  name = var.name
  # namespace - (required) is a type of string
  namespace = var.namespace
  # object - (optional) is a type of string
  object = var.object
  # time_expires - (required) is a type of string
  time_expires = var.time_expires

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_uri" {
  description = "returns a string"
  value       = oci_objectstorage_preauthrequest.this.access_uri
}

output "bucket_listing_action" {
  description = "returns a string"
  value       = oci_objectstorage_preauthrequest.this.bucket_listing_action
}

output "id" {
  description = "returns a string"
  value       = oci_objectstorage_preauthrequest.this.id
}

output "object" {
  description = "returns a string"
  value       = oci_objectstorage_preauthrequest.this.object
}

output "par_id" {
  description = "returns a string"
  value       = oci_objectstorage_preauthrequest.this.par_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_objectstorage_preauthrequest.this.time_created
}

output "this" {
  value = oci_objectstorage_preauthrequest.this
}
```

[top](#index)