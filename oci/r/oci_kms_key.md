# oci_kms_key

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
module "oci_kms_key" {
  source = "./modules/oci/r/oci_kms_key"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # desired_state - (optional) is a type of string
  desired_state = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # management_endpoint - (required) is a type of string
  management_endpoint = null
  # protection_mode - (optional) is a type of string
  protection_mode = null
  # restore_trigger - (optional) is a type of bool
  restore_trigger = null
  # time_of_deletion - (optional) is a type of string
  time_of_deletion = null

  key_shape = [{
    algorithm = null
    curve_id  = null
    length    = null
  }]

  restore_from_file = [{
    content_length                = null
    content_md5                   = null
    restore_key_from_file_details = null
  }]

  restore_from_object_store = [{
    bucket      = null
    destination = null
    namespace   = null
    object      = null
    uri         = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "desired_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "management_endpoint" {
  description = "(required)"
  type        = string
}

variable "protection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restore_trigger" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "time_of_deletion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shape" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      algorithm = string
      curve_id  = string
      length    = number
    }
  ))
}

variable "restore_from_file" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_length                = string
      content_md5                   = string
      restore_key_from_file_details = string
    }
  ))
  default = []
}

variable "restore_from_object_store" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket      = string
      destination = string
      namespace   = string
      object      = string
      uri         = string
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
resource "oci_kms_key" "this" {
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  desired_state       = var.desired_state
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  management_endpoint = var.management_endpoint
  protection_mode     = var.protection_mode
  restore_trigger     = var.restore_trigger
  time_of_deletion    = var.time_of_deletion

  dynamic "key_shape" {
    for_each = var.key_shape
    content {
      algorithm = key_shape.value["algorithm"]
      curve_id  = key_shape.value["curve_id"]
      length    = key_shape.value["length"]
    }
  }

  dynamic "restore_from_file" {
    for_each = var.restore_from_file
    content {
      content_length                = restore_from_file.value["content_length"]
      content_md5                   = restore_from_file.value["content_md5"]
      restore_key_from_file_details = restore_from_file.value["restore_key_from_file_details"]
    }
  }

  dynamic "restore_from_object_store" {
    for_each = var.restore_from_object_store
    content {
      bucket      = restore_from_object_store.value["bucket"]
      destination = restore_from_object_store.value["destination"]
      namespace   = restore_from_object_store.value["namespace"]
      object      = restore_from_object_store.value["object"]
      uri         = restore_from_object_store.value["uri"]
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
output "current_key_version" {
  description = "returns a string"
  value       = oci_kms_key.this.current_key_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_kms_key.this.defined_tags
}

output "desired_state" {
  description = "returns a string"
  value       = oci_kms_key.this.desired_state
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_kms_key.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_kms_key.this.id
}

output "is_primary" {
  description = "returns a bool"
  value       = oci_kms_key.this.is_primary
}

output "protection_mode" {
  description = "returns a string"
  value       = oci_kms_key.this.protection_mode
}

output "replica_details" {
  description = "returns a list of object"
  value       = oci_kms_key.this.replica_details
}

output "restored_from_key_id" {
  description = "returns a string"
  value       = oci_kms_key.this.restored_from_key_id
}

output "state" {
  description = "returns a string"
  value       = oci_kms_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_kms_key.this.time_created
}

output "time_of_deletion" {
  description = "returns a string"
  value       = oci_kms_key.this.time_of_deletion
}

output "vault_id" {
  description = "returns a string"
  value       = oci_kms_key.this.vault_id
}

output "this" {
  value = oci_kms_key.this
}
```

[top](#index)