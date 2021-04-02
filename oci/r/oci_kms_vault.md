# oci_kms_vault

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
module "oci_kms_vault" {
  source = "./modules/oci/r/oci_kms_vault"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # restore_trigger - (optional) is a type of bool
  restore_trigger = null
  # time_of_deletion - (optional) is a type of string
  time_of_deletion = null
  # vault_type - (required) is a type of string
  vault_type = null

  restore_from_file = [{
    content_length                  = null
    content_md5                     = null
    restore_vault_from_file_details = null
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

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
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

variable "vault_type" {
  description = "(required)"
  type        = string
}

variable "restore_from_file" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_length                  = string
      content_md5                     = string
      restore_vault_from_file_details = string
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
resource "oci_kms_vault" "this" {
  compartment_id   = var.compartment_id
  defined_tags     = var.defined_tags
  display_name     = var.display_name
  freeform_tags    = var.freeform_tags
  restore_trigger  = var.restore_trigger
  time_of_deletion = var.time_of_deletion
  vault_type       = var.vault_type

  dynamic "restore_from_file" {
    for_each = var.restore_from_file
    content {
      content_length                  = restore_from_file.value["content_length"]
      content_md5                     = restore_from_file.value["content_md5"]
      restore_vault_from_file_details = restore_from_file.value["restore_vault_from_file_details"]
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
output "crypto_endpoint" {
  description = "returns a string"
  value       = oci_kms_vault.this.crypto_endpoint
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_kms_vault.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_kms_vault.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_kms_vault.this.id
}

output "management_endpoint" {
  description = "returns a string"
  value       = oci_kms_vault.this.management_endpoint
}

output "restored_from_vault_id" {
  description = "returns a string"
  value       = oci_kms_vault.this.restored_from_vault_id
}

output "state" {
  description = "returns a string"
  value       = oci_kms_vault.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_kms_vault.this.time_created
}

output "time_of_deletion" {
  description = "returns a string"
  value       = oci_kms_vault.this.time_of_deletion
}

output "this" {
  value = oci_kms_vault.this
}
```

[top](#index)