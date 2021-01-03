# oci_ocvp_sddc

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/oci/d/oci_ocvp_sddc"

  # sddc_id - (required) is a type of string
  sddc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "sddc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_ocvp_sddc" "this" {
  sddc_id = var.sddc_id
}
```

[top](#index)

### Outputs

```terraform
output "actual_esxi_hosts_count" {
  description = "returns a number"
  value       = data.oci_ocvp_sddc.this.actual_esxi_hosts_count
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.compartment_id
}

output "compute_availability_domain" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.compute_availability_domain
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_ocvp_sddc.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.display_name
}

output "esxi_hosts_count" {
  description = "returns a number"
  value       = data.oci_ocvp_sddc.this.esxi_hosts_count
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_ocvp_sddc.this.freeform_tags
}

output "hcx_fqdn" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.hcx_fqdn
}

output "hcx_initial_password" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.hcx_initial_password
}

output "hcx_on_prem_key" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.hcx_on_prem_key
}

output "hcx_private_ip_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.hcx_private_ip_id
}

output "hcx_vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.hcx_vlan_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.id
}

output "instance_display_name_prefix" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.instance_display_name_prefix
}

output "is_hcx_enabled" {
  description = "returns a bool"
  value       = data.oci_ocvp_sddc.this.is_hcx_enabled
}

output "nsx_edge_uplink1vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_edge_uplink1vlan_id
}

output "nsx_edge_uplink2vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_edge_uplink2vlan_id
}

output "nsx_edge_uplink_ip_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_edge_uplink_ip_id
}

output "nsx_edge_vtep_vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_edge_vtep_vlan_id
}

output "nsx_manager_fqdn" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_manager_fqdn
}

output "nsx_manager_initial_password" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_manager_initial_password
}

output "nsx_manager_private_ip_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_manager_private_ip_id
}

output "nsx_manager_username" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_manager_username
}

output "nsx_overlay_segment_name" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_overlay_segment_name
}

output "nsx_vtep_vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.nsx_vtep_vlan_id
}

output "provisioning_subnet_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.provisioning_subnet_id
}

output "ssh_authorized_keys" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.ssh_authorized_keys
}

output "state" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.time_updated
}

output "vcenter_fqdn" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vcenter_fqdn
}

output "vcenter_initial_password" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vcenter_initial_password
}

output "vcenter_private_ip_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vcenter_private_ip_id
}

output "vcenter_username" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vcenter_username
}

output "vmotion_vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vmotion_vlan_id
}

output "vmware_software_version" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vmware_software_version
}

output "vsan_vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vsan_vlan_id
}

output "vsphere_vlan_id" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.vsphere_vlan_id
}

output "workload_network_cidr" {
  description = "returns a string"
  value       = data.oci_ocvp_sddc.this.workload_network_cidr
}

output "this" {
  value = oci_ocvp_sddc.this
}
```

[top](#index)