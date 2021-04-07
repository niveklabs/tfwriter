# oci_core_volume_group_backup

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
module "oci_core_volume_group_backup" {
  source = "./modules/oci/r/oci_core_volume_group_backup"

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
  # volume_group_id - (required) is a type of string
  volume_group_id = null

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

variable "volume_group_id" {
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
resource "oci_core_volume_group_backup" "this" {
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
  # volume_group_id - (required) is a type of string
  volume_group_id = var.volume_group_id

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_volume_group_backup.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.display_name
}

output "expiration_time" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.expiration_time
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_volume_group_backup.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.id
}

output "size_in_gbs" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.size_in_gbs
}

output "size_in_mbs" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.size_in_mbs
}

output "source_type" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.source_type
}

output "source_volume_group_backup_id" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.source_volume_group_backup_id
}

output "state" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.time_created
}

output "time_request_received" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.time_request_received
}

output "type" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.type
}

output "unique_size_in_gbs" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.unique_size_in_gbs
}

output "unique_size_in_mbs" {
  description = "returns a string"
  value       = oci_core_volume_group_backup.this.unique_size_in_mbs
}

output "volume_backup_ids" {
  description = "returns a list of string"
  value       = oci_core_volume_group_backup.this.volume_backup_ids
}

output "this" {
  value = oci_core_volume_group_backup.this
}
```

[top](#index)