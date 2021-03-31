# vsphere_ovf_vm_template

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_ovf_vm_template" {
  source = "./modules/vsphere/d/vsphere_ovf_vm_template"

  # allow_unverified_ssl_cert - (optional) is a type of bool
  allow_unverified_ssl_cert = null
  # datastore_id - (optional) is a type of string
  datastore_id = null
  # deployment_option - (optional) is a type of string
  deployment_option = null
  # disk_provisioning - (optional) is a type of string
  disk_provisioning = null
  # folder - (optional) is a type of string
  folder = null
  # host_system_id - (required) is a type of string
  host_system_id = null
  # ip_allocation_policy - (optional) is a type of string
  ip_allocation_policy = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # local_ovf_path - (optional) is a type of string
  local_ovf_path = null
  # name - (required) is a type of string
  name = null
  # ovf_network_map - (optional) is a type of map of string
  ovf_network_map = {}
  # remote_ovf_url - (optional) is a type of string
  remote_ovf_url = null
  # resource_pool_id - (required) is a type of string
  resource_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_unverified_ssl_cert" {
  description = "(optional) - Allow unverified ssl certificates while deploying ovf/ova from url."
  type        = bool
  default     = null
}

variable "datastore_id" {
  description = "(optional) - The ID of the virtual machine's datastore. The virtual machine configuration is placed here, along with any virtual disks that are created without datastores."
  type        = string
  default     = null
}

variable "deployment_option" {
  description = "(optional) - The Deployment option to be chosen. If empty, the default option is used."
  type        = string
  default     = null
}

variable "disk_provisioning" {
  description = "(optional) - An optional disk provisioning. If set, all the disks in the deployed ovf will have the same specified disk type (e.g., thin provisioned)."
  type        = string
  default     = null
}

variable "folder" {
  description = "(optional) - The name of the folder to locate the virtual machine in."
  type        = string
  default     = null
}

variable "host_system_id" {
  description = "(required) - The ID of an optional host system to pin the virtual machine to."
  type        = string
}

variable "ip_allocation_policy" {
  description = "(optional) - The IP allocation policy."
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional) - The IP protocol."
  type        = string
  default     = null
}

variable "local_ovf_path" {
  description = "(optional) - The absolute path to the ovf/ova file in the local system."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the virtual machine to create."
  type        = string
}

variable "ovf_network_map" {
  description = "(optional) - The mapping of name of network identifiers from the ovf descriptor to network UUID in the VI infrastructure."
  type        = map(string)
  default     = null
}

variable "remote_ovf_url" {
  description = "(optional) - URL to the remote ovf/ova file to be deployed."
  type        = string
  default     = null
}

variable "resource_pool_id" {
  description = "(required) - The ID of a resource pool to put the virtual machine in."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_ovf_vm_template" "this" {
  allow_unverified_ssl_cert = var.allow_unverified_ssl_cert
  datastore_id              = var.datastore_id
  deployment_option         = var.deployment_option
  disk_provisioning         = var.disk_provisioning
  folder                    = var.folder
  host_system_id            = var.host_system_id
  ip_allocation_policy      = var.ip_allocation_policy
  ip_protocol               = var.ip_protocol
  local_ovf_path            = var.local_ovf_path
  name                      = var.name
  ovf_network_map           = var.ovf_network_map
  remote_ovf_url            = var.remote_ovf_url
  resource_pool_id          = var.resource_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "alternate_guest_name" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.alternate_guest_name
}

output "annotation" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.annotation
}

output "cpu_hot_add_enabled" {
  description = "returns a bool"
  value       = data.vsphere_ovf_vm_template.this.cpu_hot_add_enabled
}

output "cpu_hot_remove_enabled" {
  description = "returns a bool"
  value       = data.vsphere_ovf_vm_template.this.cpu_hot_remove_enabled
}

output "cpu_performance_counters_enabled" {
  description = "returns a bool"
  value       = data.vsphere_ovf_vm_template.this.cpu_performance_counters_enabled
}

output "firmware" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.firmware
}

output "guest_id" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.guest_id
}

output "id" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.id
}

output "ide_controller_count" {
  description = "returns a number"
  value       = data.vsphere_ovf_vm_template.this.ide_controller_count
}

output "memory" {
  description = "returns a number"
  value       = data.vsphere_ovf_vm_template.this.memory
}

output "memory_hot_add_enabled" {
  description = "returns a bool"
  value       = data.vsphere_ovf_vm_template.this.memory_hot_add_enabled
}

output "nested_hv_enabled" {
  description = "returns a bool"
  value       = data.vsphere_ovf_vm_template.this.nested_hv_enabled
}

output "num_cores_per_socket" {
  description = "returns a number"
  value       = data.vsphere_ovf_vm_template.this.num_cores_per_socket
}

output "num_cpus" {
  description = "returns a number"
  value       = data.vsphere_ovf_vm_template.this.num_cpus
}

output "sata_controller_count" {
  description = "returns a number"
  value       = data.vsphere_ovf_vm_template.this.sata_controller_count
}

output "scsi_controller_count" {
  description = "returns a number"
  value       = data.vsphere_ovf_vm_template.this.scsi_controller_count
}

output "scsi_type" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.scsi_type
}

output "swap_placement_policy" {
  description = "returns a string"
  value       = data.vsphere_ovf_vm_template.this.swap_placement_policy
}

output "this" {
  value = vsphere_ovf_vm_template.this
}
```

[top](#index)