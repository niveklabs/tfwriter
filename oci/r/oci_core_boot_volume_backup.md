# oci_core_boot_volume_backup

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
module "oci_core_boot_volume_backup" {
  source = "./modules/oci/r/oci_core_boot_volume_backup"

  # boot_volume_id - (optional) is a type of string
  boot_volume_id = null
  # compartment_id - (optional) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # type - (optional) is a type of string
  type = null

  source_details = [{
    boot_volume_backup_id = null
    kms_key_id            = null
    region                = null
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
variable "boot_volume_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      boot_volume_backup_id = string
      kms_key_id            = string
      region                = string
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
resource "oci_core_boot_volume_backup" "this" {
  # boot_volume_id - (optional) is a type of string
  boot_volume_id = var.boot_volume_id
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # type - (optional) is a type of string
  type = var.type

  dynamic "source_details" {
    for_each = var.source_details
    content {
      # boot_volume_backup_id - (required) is a type of string
      boot_volume_backup_id = source_details.value["boot_volume_backup_id"]
      # kms_key_id - (optional) is a type of string
      kms_key_id = source_details.value["kms_key_id"]
      # region - (required) is a type of string
      region = source_details.value["region"]
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
output "boot_volume_id" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.boot_volume_id
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_boot_volume_backup.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.display_name
}

output "expiration_time" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.expiration_time
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_boot_volume_backup.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.id
}

output "image_id" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.image_id
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.kms_key_id
}

output "size_in_gbs" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.size_in_gbs
}

output "source_boot_volume_backup_id" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.source_boot_volume_backup_id
}

output "source_type" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.source_type
}

output "state" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_core_boot_volume_backup.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.time_created
}

output "time_request_received" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.time_request_received
}

output "type" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.type
}

output "unique_size_in_gbs" {
  description = "returns a string"
  value       = oci_core_boot_volume_backup.this.unique_size_in_gbs
}

output "this" {
  value = oci_core_boot_volume_backup.this
}
```

[top](#index)