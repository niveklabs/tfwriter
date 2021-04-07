# oci_core_boot_volume

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
module "oci_core_boot_volume" {
  source = "./modules/oci/r/oci_core_boot_volume"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # backup_policy_id - (optional) is a type of string
  backup_policy_id = null
  # boot_volume_replicas_deletion - (optional) is a type of bool
  boot_volume_replicas_deletion = null
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
  # vpus_per_gb - (optional) is a type of string
  vpus_per_gb = null

  boot_volume_replicas = [{
    availability_domain    = null
    boot_volume_replica_id = null
    display_name           = null
  }]

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

variable "boot_volume_replicas_deletion" {
  description = "(optional)"
  type        = bool
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

variable "vpus_per_gb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "boot_volume_replicas" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      availability_domain    = string
      boot_volume_replica_id = string
      display_name           = string
    }
  ))
  default = []
}

variable "source_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      id   = string
      type = string
    }
  ))
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
resource "oci_core_boot_volume" "this" {
  # availability_domain - (required) is a type of string
  availability_domain = var.availability_domain
  # backup_policy_id - (optional) is a type of string
  backup_policy_id = var.backup_policy_id
  # boot_volume_replicas_deletion - (optional) is a type of bool
  boot_volume_replicas_deletion = var.boot_volume_replicas_deletion
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # is_auto_tune_enabled - (optional) is a type of bool
  is_auto_tune_enabled = var.is_auto_tune_enabled
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # size_in_gbs - (optional) is a type of string
  size_in_gbs = var.size_in_gbs
  # vpus_per_gb - (optional) is a type of string
  vpus_per_gb = var.vpus_per_gb

  dynamic "boot_volume_replicas" {
    for_each = var.boot_volume_replicas
    content {
      # availability_domain - (required) is a type of string
      availability_domain = boot_volume_replicas.value["availability_domain"]
      # display_name - (optional) is a type of string
      display_name = boot_volume_replicas.value["display_name"]
    }
  }

  dynamic "source_details" {
    for_each = var.source_details
    content {
      # id - (required) is a type of string
      id = source_details.value["id"]
      # type - (required) is a type of string
      type = source_details.value["type"]
    }
  }

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
output "auto_tuned_vpus_per_gb" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.auto_tuned_vpus_per_gb
}

output "backup_policy_id" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.backup_policy_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_boot_volume.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_boot_volume.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.id
}

output "image_id" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.image_id
}

output "is_auto_tune_enabled" {
  description = "returns a bool"
  value       = oci_core_boot_volume.this.is_auto_tune_enabled
}

output "is_hydrated" {
  description = "returns a bool"
  value       = oci_core_boot_volume.this.is_hydrated
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.kms_key_id
}

output "size_in_gbs" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.size_in_gbs
}

output "size_in_mbs" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.size_in_mbs
}

output "state" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_core_boot_volume.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.time_created
}

output "volume_group_id" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.volume_group_id
}

output "vpus_per_gb" {
  description = "returns a string"
  value       = oci_core_boot_volume.this.vpus_per_gb
}

output "this" {
  value = oci_core_boot_volume.this
}
```

[top](#index)