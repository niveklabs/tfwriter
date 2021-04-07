# oci_objectstorage_replication_policy

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_replication_policy" {
  source = "./modules/oci/d/oci_objectstorage_replication_policy"

  # bucket - (required) is a type of string
  bucket = null
  # namespace - (required) is a type of string
  namespace = null
  # replication_id - (required) is a type of string
  replication_id = null
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

variable "replication_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_replication_policy" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # namespace - (required) is a type of string
  namespace = var.namespace
  # replication_id - (required) is a type of string
  replication_id = var.replication_id
}
```

[top](#index)

### Outputs

```terraform
output "delete_object_in_destination_bucket" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.delete_object_in_destination_bucket
}

output "destination_bucket_name" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.destination_bucket_name
}

output "destination_region_name" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.destination_region_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.name
}

output "status" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.status
}

output "status_message" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.status_message
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.time_created
}

output "time_last_sync" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policy.this.time_last_sync
}

output "this" {
  value = oci_objectstorage_replication_policy.this
}
```

[top](#index)