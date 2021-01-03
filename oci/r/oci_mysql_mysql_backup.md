# oci_mysql_mysql_backup

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_mysql_mysql_backup" {
  source = "./modules/oci/r/oci_mysql_mysql_backup"

  # backup_type - (optional) is a type of string
  backup_type = null
  # db_system_id - (required) is a type of string
  db_system_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # retention_in_days - (optional) is a type of number
  retention_in_days = null

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
variable "backup_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_system_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
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

variable "retention_in_days" {
  description = "(optional)"
  type        = number
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
resource "oci_mysql_mysql_backup" "this" {
  backup_type       = var.backup_type
  db_system_id      = var.db_system_id
  defined_tags      = var.defined_tags
  description       = var.description
  display_name      = var.display_name
  freeform_tags     = var.freeform_tags
  retention_in_days = var.retention_in_days

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
output "backup_size_in_gbs" {
  description = "returns a number"
  value       = oci_mysql_mysql_backup.this.backup_size_in_gbs
}

output "backup_type" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.backup_type
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.compartment_id
}

output "creation_type" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.creation_type
}

output "data_storage_size_in_gb" {
  description = "returns a number"
  value       = oci_mysql_mysql_backup.this.data_storage_size_in_gb
}

output "db_system_snapshot" {
  description = "returns a list of object"
  value       = oci_mysql_mysql_backup.this.db_system_snapshot
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_mysql_mysql_backup.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_mysql_mysql_backup.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.lifecycle_details
}

output "mysql_version" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.mysql_version
}

output "retention_in_days" {
  description = "returns a number"
  value       = oci_mysql_mysql_backup.this.retention_in_days
}

output "shape_name" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.shape_name
}

output "state" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_mysql_mysql_backup.this.time_updated
}

output "this" {
  value = oci_mysql_mysql_backup.this
}
```

[top](#index)