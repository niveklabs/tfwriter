# oci_database_data_guard_association

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_data_guard_association" {
  source = "./modules/oci/r/oci_database_data_guard_association"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # backup_network_nsg_ids - (optional) is a type of set of string
  backup_network_nsg_ids = []
  # creation_type - (required) is a type of string
  creation_type = null
  # database_admin_password - (required) is a type of string
  database_admin_password = null
  # database_id - (required) is a type of string
  database_id = null
  # database_software_image_id - (optional) is a type of string
  database_software_image_id = null
  # delete_standby_db_home_on_delete - (required) is a type of string
  delete_standby_db_home_on_delete = null
  # display_name - (optional) is a type of string
  display_name = null
  # hostname - (optional) is a type of string
  hostname = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # peer_db_home_id - (optional) is a type of string
  peer_db_home_id = null
  # peer_db_system_id - (optional) is a type of string
  peer_db_system_id = null
  # peer_vm_cluster_id - (optional) is a type of string
  peer_vm_cluster_id = null
  # protection_mode - (required) is a type of string
  protection_mode = null
  # shape - (optional) is a type of string
  shape = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # transport_type - (required) is a type of string
  transport_type = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_network_nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "creation_type" {
  description = "(required)"
  type        = string
}

variable "database_admin_password" {
  description = "(required)"
  type        = string
}

variable "database_id" {
  description = "(required)"
  type        = string
}

variable "database_software_image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_standby_db_home_on_delete" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "peer_db_home_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_vm_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protection_mode" {
  description = "(required)"
  type        = string
}

variable "shape" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transport_type" {
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
resource "oci_database_data_guard_association" "this" {
  availability_domain              = var.availability_domain
  backup_network_nsg_ids           = var.backup_network_nsg_ids
  creation_type                    = var.creation_type
  database_admin_password          = var.database_admin_password
  database_id                      = var.database_id
  database_software_image_id       = var.database_software_image_id
  delete_standby_db_home_on_delete = var.delete_standby_db_home_on_delete
  display_name                     = var.display_name
  hostname                         = var.hostname
  nsg_ids                          = var.nsg_ids
  peer_db_home_id                  = var.peer_db_home_id
  peer_db_system_id                = var.peer_db_system_id
  peer_vm_cluster_id               = var.peer_vm_cluster_id
  protection_mode                  = var.protection_mode
  shape                            = var.shape
  subnet_id                        = var.subnet_id
  transport_type                   = var.transport_type

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
output "apply_lag" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.apply_lag
}

output "apply_rate" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.apply_rate
}

output "availability_domain" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.availability_domain
}

output "display_name" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.display_name
}

output "hostname" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.hostname
}

output "id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.lifecycle_details
}

output "peer_data_guard_association_id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.peer_data_guard_association_id
}

output "peer_database_id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.peer_database_id
}

output "peer_db_home_id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.peer_db_home_id
}

output "peer_db_system_id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.peer_db_system_id
}

output "peer_role" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.peer_role
}

output "peer_vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.peer_vm_cluster_id
}

output "role" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.role
}

output "shape" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.shape
}

output "state" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_data_guard_association.this.time_created
}

output "this" {
  value = oci_database_data_guard_association.this
}
```

[top](#index)