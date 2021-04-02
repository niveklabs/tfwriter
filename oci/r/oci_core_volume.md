# oci_core_volume

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
module "oci_core_volume" {
  source = "./modules/oci/r/oci_core_volume"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # backup_policy_id - (optional) is a type of string
  backup_policy_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_auto_tune_enabled - (optional) is a type of bool
  is_auto_tune_enabled = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # size_in_gbs - (optional) is a type of string
  size_in_gbs = null
  # size_in_mbs - (optional) is a type of string
  size_in_mbs = null
  # volume_backup_id - (optional) is a type of string
  volume_backup_id = null
  # vpus_per_gb - (optional) is a type of string
  vpus_per_gb = null

  source_details = [{
    id   = null
    type = null
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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "backup_policy_id" {
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

variable "is_auto_tune_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size_in_gbs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size_in_mbs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpus_per_gb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id   = string
      type = string
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
resource "oci_core_volume" "this" {
  availability_domain  = var.availability_domain
  backup_policy_id     = var.backup_policy_id
  compartment_id       = var.compartment_id
  defined_tags         = var.defined_tags
  display_name         = var.display_name
  freeform_tags        = var.freeform_tags
  is_auto_tune_enabled = var.is_auto_tune_enabled
  kms_key_id           = var.kms_key_id
  size_in_gbs          = var.size_in_gbs
  size_in_mbs          = var.size_in_mbs
  volume_backup_id     = var.volume_backup_id
  vpus_per_gb          = var.vpus_per_gb

  dynamic "source_details" {
    for_each = var.source_details
    content {
      id   = source_details.value["id"]
      type = source_details.value["type"]
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
output "auto_tuned_vpus_per_gb" {
  description = "returns a string"
  value       = oci_core_volume.this.auto_tuned_vpus_per_gb
}

output "backup_policy_id" {
  description = "returns a string"
  value       = oci_core_volume.this.backup_policy_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_volume.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_volume.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_volume.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_volume.this.id
}

output "is_auto_tune_enabled" {
  description = "returns a bool"
  value       = oci_core_volume.this.is_auto_tune_enabled
}

output "is_hydrated" {
  description = "returns a bool"
  value       = oci_core_volume.this.is_hydrated
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_core_volume.this.kms_key_id
}

output "size_in_gbs" {
  description = "returns a string"
  value       = oci_core_volume.this.size_in_gbs
}

output "size_in_mbs" {
  description = "returns a string"
  value       = oci_core_volume.this.size_in_mbs
}

output "state" {
  description = "returns a string"
  value       = oci_core_volume.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_core_volume.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_volume.this.time_created
}

output "volume_backup_id" {
  description = "returns a string"
  value       = oci_core_volume.this.volume_backup_id
}

output "volume_group_id" {
  description = "returns a string"
  value       = oci_core_volume.this.volume_group_id
}

output "vpus_per_gb" {
  description = "returns a string"
  value       = oci_core_volume.this.vpus_per_gb
}

output "this" {
  value = oci_core_volume.this
}
```

[top](#index)