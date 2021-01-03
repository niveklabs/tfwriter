# oci_ocvp_sddc

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
module "oci_ocvp_sddc" {
  source = "./modules/oci/r/oci_ocvp_sddc"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compute_availability_domain - (required) is a type of string
  compute_availability_domain = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # esxi_hosts_count - (required) is a type of number
  esxi_hosts_count = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hcx_vlan_id - (optional) is a type of string
  hcx_vlan_id = null
  # instance_display_name_prefix - (optional) is a type of string
  instance_display_name_prefix = null
  # is_hcx_enabled - (optional) is a type of bool
  is_hcx_enabled = null
  # nsx_edge_uplink1vlan_id - (required) is a type of string
  nsx_edge_uplink1vlan_id = null
  # nsx_edge_uplink2vlan_id - (required) is a type of string
  nsx_edge_uplink2vlan_id = null
  # nsx_edge_vtep_vlan_id - (required) is a type of string
  nsx_edge_vtep_vlan_id = null
  # nsx_vtep_vlan_id - (required) is a type of string
  nsx_vtep_vlan_id = null
  # provisioning_subnet_id - (required) is a type of string
  provisioning_subnet_id = null
  # ssh_authorized_keys - (required) is a type of string
  ssh_authorized_keys = null
  # vmotion_vlan_id - (required) is a type of string
  vmotion_vlan_id = null
  # vmware_software_version - (required) is a type of string
  vmware_software_version = null
  # vsan_vlan_id - (required) is a type of string
  vsan_vlan_id = null
  # vsphere_vlan_id - (required) is a type of string
  vsphere_vlan_id = null
  # workload_network_cidr - (optional) is a type of string
  workload_network_cidr = null

  timeouts = [{
    create = null
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

variable "compute_availability_domain" {
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

variable "esxi_hosts_count" {
  description = "(required)"
  type        = number
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hcx_vlan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_display_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_hcx_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "nsx_edge_uplink1vlan_id" {
  description = "(required)"
  type        = string
}

variable "nsx_edge_uplink2vlan_id" {
  description = "(required)"
  type        = string
}

variable "nsx_edge_vtep_vlan_id" {
  description = "(required)"
  type        = string
}

variable "nsx_vtep_vlan_id" {
  description = "(required)"
  type        = string
}

variable "provisioning_subnet_id" {
  description = "(required)"
  type        = string
}

variable "ssh_authorized_keys" {
  description = "(required)"
  type        = string
}

variable "vmotion_vlan_id" {
  description = "(required)"
  type        = string
}

variable "vmware_software_version" {
  description = "(required)"
  type        = string
}

variable "vsan_vlan_id" {
  description = "(required)"
  type        = string
}

variable "vsphere_vlan_id" {
  description = "(required)"
  type        = string
}

variable "workload_network_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_ocvp_sddc" "this" {
  compartment_id               = var.compartment_id
  compute_availability_domain  = var.compute_availability_domain
  defined_tags                 = var.defined_tags
  display_name                 = var.display_name
  esxi_hosts_count             = var.esxi_hosts_count
  freeform_tags                = var.freeform_tags
  hcx_vlan_id                  = var.hcx_vlan_id
  instance_display_name_prefix = var.instance_display_name_prefix
  is_hcx_enabled               = var.is_hcx_enabled
  nsx_edge_uplink1vlan_id      = var.nsx_edge_uplink1vlan_id
  nsx_edge_uplink2vlan_id      = var.nsx_edge_uplink2vlan_id
  nsx_edge_vtep_vlan_id        = var.nsx_edge_vtep_vlan_id
  nsx_vtep_vlan_id             = var.nsx_vtep_vlan_id
  provisioning_subnet_id       = var.provisioning_subnet_id
  ssh_authorized_keys          = var.ssh_authorized_keys
  vmotion_vlan_id              = var.vmotion_vlan_id
  vmware_software_version      = var.vmware_software_version
  vsan_vlan_id                 = var.vsan_vlan_id
  vsphere_vlan_id              = var.vsphere_vlan_id
  workload_network_cidr        = var.workload_network_cidr

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "actual_esxi_hosts_count" {
  description = "returns a number"
  value       = oci_ocvp_sddc.this.actual_esxi_hosts_count
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_ocvp_sddc.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_ocvp_sddc.this.freeform_tags
}

output "hcx_fqdn" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.hcx_fqdn
}

output "hcx_initial_password" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.hcx_initial_password
}

output "hcx_on_prem_key" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.hcx_on_prem_key
}

output "hcx_private_ip_id" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.hcx_private_ip_id
}

output "hcx_vlan_id" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.hcx_vlan_id
}

output "id" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.id
}

output "instance_display_name_prefix" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.instance_display_name_prefix
}

output "is_hcx_enabled" {
  description = "returns a bool"
  value       = oci_ocvp_sddc.this.is_hcx_enabled
}

output "nsx_edge_uplink_ip_id" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.nsx_edge_uplink_ip_id
}

output "nsx_manager_fqdn" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.nsx_manager_fqdn
}

output "nsx_manager_initial_password" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.nsx_manager_initial_password
}

output "nsx_manager_private_ip_id" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.nsx_manager_private_ip_id
}

output "nsx_manager_username" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.nsx_manager_username
}

output "nsx_overlay_segment_name" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.nsx_overlay_segment_name
}

output "state" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.time_updated
}

output "vcenter_fqdn" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.vcenter_fqdn
}

output "vcenter_initial_password" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.vcenter_initial_password
}

output "vcenter_private_ip_id" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.vcenter_private_ip_id
}

output "vcenter_username" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.vcenter_username
}

output "workload_network_cidr" {
  description = "returns a string"
  value       = oci_ocvp_sddc.this.workload_network_cidr
}

output "this" {
  value = oci_ocvp_sddc.this
}
```

[top](#index)