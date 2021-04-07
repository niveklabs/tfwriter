# oci_file_storage_file_system

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
module "oci_file_storage_file_system" {
  source = "./modules/oci/r/oci_file_storage_file_system"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # source_snapshot_id - (optional) is a type of string
  source_snapshot_id = null

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
variable "availability_domain" {
  description = "(required)"
  type        = string
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

variable "display_name" {
  description = "(optional)"
  type        = string
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

variable "source_snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_file_storage_file_system" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  kms_key_id          = var.kms_key_id
  source_snapshot_id  = var.source_snapshot_id

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_file_storage_file_system.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_file_storage_file_system.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.id
}

output "is_clone_parent" {
  description = "returns a bool"
  value       = oci_file_storage_file_system.this.is_clone_parent
}

output "is_hydrated" {
  description = "returns a bool"
  value       = oci_file_storage_file_system.this.is_hydrated
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.lifecycle_details
}

output "metered_bytes" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.metered_bytes
}

output "source_details" {
  description = "returns a list of object"
  value       = oci_file_storage_file_system.this.source_details
}

output "source_snapshot_id" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.source_snapshot_id
}

output "state" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_file_storage_file_system.this.time_created
}

output "this" {
  value = oci_file_storage_file_system.this
}
```

[top](#index)