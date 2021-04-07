# oci_objectstorage_bucket

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
module "oci_objectstorage_bucket" {
  source = "./modules/oci/r/oci_objectstorage_bucket"

  # access_type - (optional) is a type of string
  access_type = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # namespace - (required) is a type of string
  namespace = null
  # object_events_enabled - (optional) is a type of bool
  object_events_enabled = null
  # storage_tier - (optional) is a type of string
  storage_tier = null
  # versioning - (optional) is a type of string
  versioning = null

  retention_rules = [{
    display_name = null
    duration = [{
      time_amount = null
      time_unit   = null
    }]
    retention_rule_id = null
    time_created      = null
    time_modified     = null
    time_rule_locked  = null
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
variable "access_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
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

variable "object_events_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "versioning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retention_rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      display_name = string
      duration = list(object(
        {
          time_amount = string
          time_unit   = string
        }
      ))
      retention_rule_id = string
      time_created      = string
      time_modified     = string
      time_rule_locked  = string
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
resource "oci_objectstorage_bucket" "this" {
  access_type           = var.access_type
  compartment_id        = var.compartment_id
  defined_tags          = var.defined_tags
  freeform_tags         = var.freeform_tags
  kms_key_id            = var.kms_key_id
  metadata              = var.metadata
  name                  = var.name
  namespace             = var.namespace
  object_events_enabled = var.object_events_enabled
  storage_tier          = var.storage_tier
  versioning            = var.versioning

  dynamic "retention_rules" {
    for_each = var.retention_rules
    content {
      display_name     = retention_rules.value["display_name"]
      time_rule_locked = retention_rules.value["time_rule_locked"]

      dynamic "duration" {
        for_each = retention_rules.value.duration
        content {
          time_amount = duration.value["time_amount"]
          time_unit   = duration.value["time_unit"]
        }
      }

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
output "approximate_count" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.approximate_count
}

output "approximate_size" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.approximate_size
}

output "bucket_id" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.bucket_id
}

output "created_by" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_objectstorage_bucket.this.defined_tags
}

output "etag" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.etag
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_objectstorage_bucket.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.id
}

output "is_read_only" {
  description = "returns a bool"
  value       = oci_objectstorage_bucket.this.is_read_only
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.kms_key_id
}

output "object_events_enabled" {
  description = "returns a bool"
  value       = oci_objectstorage_bucket.this.object_events_enabled
}

output "object_lifecycle_policy_etag" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.object_lifecycle_policy_etag
}

output "replication_enabled" {
  description = "returns a bool"
  value       = oci_objectstorage_bucket.this.replication_enabled
}

output "storage_tier" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.storage_tier
}

output "time_created" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.time_created
}

output "versioning" {
  description = "returns a string"
  value       = oci_objectstorage_bucket.this.versioning
}

output "this" {
  value = oci_objectstorage_bucket.this
}
```

[top](#index)