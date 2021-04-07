# oci_database_backup_destination

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
module "oci_database_backup_destination" {
  source = "./modules/oci/r/oci_database_backup_destination"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # connection_string - (optional) is a type of string
  connection_string = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # local_mount_point_path - (optional) is a type of string
  local_mount_point_path = null
  # type - (required) is a type of string
  type = null
  # vpc_users - (optional) is a type of list of string
  vpc_users = []

  mount_type_details = [{
    local_mount_point_path = null
    mount_type             = null
    nfs_server             = []
    nfs_server_export      = null
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

variable "connection_string" {
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
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "local_mount_point_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "vpc_users" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "mount_type_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      local_mount_point_path = string
      mount_type             = string
      nfs_server             = list(string)
      nfs_server_export      = string
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
resource "oci_database_backup_destination" "this" {
  compartment_id         = var.compartment_id
  connection_string      = var.connection_string
  defined_tags           = var.defined_tags
  display_name           = var.display_name
  freeform_tags          = var.freeform_tags
  local_mount_point_path = var.local_mount_point_path
  type                   = var.type
  vpc_users              = var.vpc_users

  dynamic "mount_type_details" {
    for_each = var.mount_type_details
    content {
      local_mount_point_path = mount_type_details.value["local_mount_point_path"]
      mount_type             = mount_type_details.value["mount_type"]
      nfs_server             = mount_type_details.value["nfs_server"]
      nfs_server_export      = mount_type_details.value["nfs_server_export"]
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
output "associated_databases" {
  description = "returns a list of object"
  value       = oci_database_backup_destination.this.associated_databases
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_backup_destination.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_backup_destination.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.lifecycle_details
}

output "local_mount_point_path" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.local_mount_point_path
}

output "nfs_mount_type" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.nfs_mount_type
}

output "nfs_server" {
  description = "returns a list of string"
  value       = oci_database_backup_destination.this.nfs_server
}

output "nfs_server_export" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.nfs_server_export
}

output "state" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_backup_destination.this.time_created
}

output "this" {
  value = oci_database_backup_destination.this
}
```

[top](#index)