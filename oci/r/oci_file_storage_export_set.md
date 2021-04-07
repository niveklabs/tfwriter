# oci_file_storage_export_set

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
module "oci_file_storage_export_set" {
  source = "./modules/oci/r/oci_file_storage_export_set"

  # display_name - (optional) is a type of string
  display_name = null
  # max_fs_stat_bytes - (optional) is a type of string
  max_fs_stat_bytes = null
  # max_fs_stat_files - (optional) is a type of string
  max_fs_stat_files = null
  # mount_target_id - (required) is a type of string
  mount_target_id = null

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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_fs_stat_bytes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_fs_stat_files" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mount_target_id" {
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
resource "oci_file_storage_export_set" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # max_fs_stat_bytes - (optional) is a type of string
  max_fs_stat_bytes = var.max_fs_stat_bytes
  # max_fs_stat_files - (optional) is a type of string
  max_fs_stat_files = var.max_fs_stat_files
  # mount_target_id - (required) is a type of string
  mount_target_id = var.mount_target_id

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
output "availability_domain" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.compartment_id
}

output "display_name" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.id
}

output "max_fs_stat_bytes" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.max_fs_stat_bytes
}

output "max_fs_stat_files" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.max_fs_stat_files
}

output "state" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.time_created
}

output "vcn_id" {
  description = "returns a string"
  value       = oci_file_storage_export_set.this.vcn_id
}

output "this" {
  value = oci_file_storage_export_set.this
}
```

[top](#index)