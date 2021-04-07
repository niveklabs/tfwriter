# oci_database_autonomous_vm_cluster

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
module "oci_database_autonomous_vm_cluster" {
  source = "./modules/oci/r/oci_database_autonomous_vm_cluster"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_local_backup_enabled - (optional) is a type of bool
  is_local_backup_enabled = null
  # license_model - (optional) is a type of string
  license_model = null
  # time_zone - (optional) is a type of string
  time_zone = null
  # vm_cluster_network_id - (required) is a type of string
  vm_cluster_network_id = null

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

variable "exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_local_backup_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_cluster_network_id" {
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
resource "oci_database_autonomous_vm_cluster" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = var.exadata_infrastructure_id
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # is_local_backup_enabled - (optional) is a type of bool
  is_local_backup_enabled = var.is_local_backup_enabled
  # license_model - (optional) is a type of string
  license_model = var.license_model
  # time_zone - (optional) is a type of string
  time_zone = var.time_zone
  # vm_cluster_network_id - (required) is a type of string
  vm_cluster_network_id = var.vm_cluster_network_id

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
output "available_cpus" {
  description = "returns a number"
  value       = oci_database_autonomous_vm_cluster.this.available_cpus
}

output "available_data_storage_size_in_tbs" {
  description = "returns a number"
  value       = oci_database_autonomous_vm_cluster.this.available_data_storage_size_in_tbs
}

output "cpus_enabled" {
  description = "returns a number"
  value       = oci_database_autonomous_vm_cluster.this.cpus_enabled
}

output "data_storage_size_in_tbs" {
  description = "returns a number"
  value       = oci_database_autonomous_vm_cluster.this.data_storage_size_in_tbs
}

output "db_node_storage_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_autonomous_vm_cluster.this.db_node_storage_size_in_gbs
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_vm_cluster.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_autonomous_vm_cluster.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_autonomous_vm_cluster.this.id
}

output "is_local_backup_enabled" {
  description = "returns a bool"
  value       = oci_database_autonomous_vm_cluster.this.is_local_backup_enabled
}

output "license_model" {
  description = "returns a string"
  value       = oci_database_autonomous_vm_cluster.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_autonomous_vm_cluster.this.lifecycle_details
}

output "memory_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_autonomous_vm_cluster.this.memory_size_in_gbs
}

output "state" {
  description = "returns a string"
  value       = oci_database_autonomous_vm_cluster.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_autonomous_vm_cluster.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = oci_database_autonomous_vm_cluster.this.time_zone
}

output "this" {
  value = oci_database_autonomous_vm_cluster.this
}
```

[top](#index)