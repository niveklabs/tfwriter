# oci_objectstorage_replication_policy

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
module "oci_objectstorage_replication_policy" {
  source = "./modules/oci/r/oci_objectstorage_replication_policy"

  # bucket - (required) is a type of string
  bucket = null
  # delete_object_in_destination_bucket - (optional) is a type of string
  delete_object_in_destination_bucket = null
  # destination_bucket_name - (required) is a type of string
  destination_bucket_name = null
  # destination_region_name - (required) is a type of string
  destination_region_name = null
  # name - (required) is a type of string
  name = null
  # namespace - (required) is a type of string
  namespace = null

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

variable "delete_object_in_destination_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_bucket_name" {
  description = "(required)"
  type        = string
}

variable "destination_region_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
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
resource "oci_objectstorage_replication_policy" "this" {
  bucket                              = var.bucket
  delete_object_in_destination_bucket = var.delete_object_in_destination_bucket
  destination_bucket_name             = var.destination_bucket_name
  destination_region_name             = var.destination_region_name
  name                                = var.name
  namespace                           = var.namespace

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
output "id" {
  description = "returns a string"
  value       = oci_objectstorage_replication_policy.this.id
}

output "status" {
  description = "returns a string"
  value       = oci_objectstorage_replication_policy.this.status
}

output "status_message" {
  description = "returns a string"
  value       = oci_objectstorage_replication_policy.this.status_message
}

output "time_created" {
  description = "returns a string"
  value       = oci_objectstorage_replication_policy.this.time_created
}

output "time_last_sync" {
  description = "returns a string"
  value       = oci_objectstorage_replication_policy.this.time_last_sync
}

output "this" {
  value = oci_objectstorage_replication_policy.this
}
```

[top](#index)