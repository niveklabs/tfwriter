# oci_database_cloud_vm_cluster

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
module "oci_database_cloud_vm_cluster" {
  source = "./modules/oci/r/oci_database_cloud_vm_cluster"

  # backup_network_nsg_ids - (optional) is a type of set of string
  backup_network_nsg_ids = []
  # backup_subnet_id - (required) is a type of string
  backup_subnet_id = null
  # cloud_exadata_infrastructure_id - (required) is a type of string
  cloud_exadata_infrastructure_id = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpu_core_count - (required) is a type of number
  cpu_core_count = null
  # data_storage_percentage - (optional) is a type of number
  data_storage_percentage = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # gi_version - (required) is a type of string
  gi_version = null
  # hostname - (required) is a type of string
  hostname = null
  # is_local_backup_enabled - (optional) is a type of bool
  is_local_backup_enabled = null
  # is_sparse_diskgroup_enabled - (optional) is a type of bool
  is_sparse_diskgroup_enabled = null
  # license_model - (optional) is a type of string
  license_model = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # ssh_public_keys - (required) is a type of list of string
  ssh_public_keys = []
  # subnet_id - (required) is a type of string
  subnet_id = null
  # time_zone - (optional) is a type of string
  time_zone = null

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
variable "backup_network_nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_subnet_id" {
  description = "(required)"
  type        = string
}

variable "cloud_exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}

variable "cluster_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "cpu_core_count" {
  description = "(required)"
  type        = number
}

variable "data_storage_percentage" {
  description = "(optional)"
  type        = number
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

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "gi_version" {
  description = "(required)"
  type        = string
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "is_local_backup_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_sparse_diskgroup_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ssh_public_keys" {
  description = "(required)"
  type        = list(string)
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "time_zone" {
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
resource "oci_database_cloud_vm_cluster" "this" {
  backup_network_nsg_ids          = var.backup_network_nsg_ids
  backup_subnet_id                = var.backup_subnet_id
  cloud_exadata_infrastructure_id = var.cloud_exadata_infrastructure_id
  cluster_name                    = var.cluster_name
  compartment_id                  = var.compartment_id
  cpu_core_count                  = var.cpu_core_count
  data_storage_percentage         = var.data_storage_percentage
  defined_tags                    = var.defined_tags
  display_name                    = var.display_name
  domain                          = var.domain
  freeform_tags                   = var.freeform_tags
  gi_version                      = var.gi_version
  hostname                        = var.hostname
  is_local_backup_enabled         = var.is_local_backup_enabled
  is_sparse_diskgroup_enabled     = var.is_sparse_diskgroup_enabled
  license_model                   = var.license_model
  nsg_ids                         = var.nsg_ids
  ssh_public_keys                 = var.ssh_public_keys
  subnet_id                       = var.subnet_id
  time_zone                       = var.time_zone

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
output "availability_domain" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.availability_domain
}

output "backup_network_nsg_ids" {
  description = "returns a set of string"
  value       = oci_database_cloud_vm_cluster.this.backup_network_nsg_ids
}

output "cluster_name" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.cluster_name
}

output "data_storage_percentage" {
  description = "returns a number"
  value       = oci_database_cloud_vm_cluster.this.data_storage_percentage
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_cloud_vm_cluster.this.defined_tags
}

output "disk_redundancy" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.disk_redundancy
}

output "domain" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_cloud_vm_cluster.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.id
}

output "iorm_config_cache" {
  description = "returns a list of object"
  value       = oci_database_cloud_vm_cluster.this.iorm_config_cache
}

output "is_local_backup_enabled" {
  description = "returns a bool"
  value       = oci_database_cloud_vm_cluster.this.is_local_backup_enabled
}

output "is_sparse_diskgroup_enabled" {
  description = "returns a bool"
  value       = oci_database_cloud_vm_cluster.this.is_sparse_diskgroup_enabled
}

output "last_update_history_entry_id" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.last_update_history_entry_id
}

output "license_model" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.lifecycle_details
}

output "listener_port" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.listener_port
}

output "node_count" {
  description = "returns a number"
  value       = oci_database_cloud_vm_cluster.this.node_count
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_database_cloud_vm_cluster.this.nsg_ids
}

output "scan_dns_name" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.scan_dns_name
}

output "scan_dns_record_id" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.scan_dns_record_id
}

output "scan_ip_ids" {
  description = "returns a list of string"
  value       = oci_database_cloud_vm_cluster.this.scan_ip_ids
}

output "shape" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.shape
}

output "state" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.state
}

output "storage_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_cloud_vm_cluster.this.storage_size_in_gbs
}

output "system_version" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.system_version
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.time_zone
}

output "vip_ids" {
  description = "returns a list of string"
  value       = oci_database_cloud_vm_cluster.this.vip_ids
}

output "zone_id" {
  description = "returns a string"
  value       = oci_database_cloud_vm_cluster.this.zone_id
}

output "this" {
  value = oci_database_cloud_vm_cluster.this
}
```

[top](#index)