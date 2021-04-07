# aci_vmm_domain

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_vmm_domain" {
  source = "./modules/aci/r/aci_vmm_domain"

  # access_mode - (optional) is a type of string
  access_mode = null
  # annotation - (optional) is a type of string
  annotation = null
  # arp_learning - (optional) is a type of string
  arp_learning = null
  # ave_time_out - (optional) is a type of string
  ave_time_out = null
  # config_infra_pg - (optional) is a type of string
  config_infra_pg = null
  # ctrl_knob - (optional) is a type of string
  ctrl_knob = null
  # delimiter - (optional) is a type of string
  delimiter = null
  # description - (optional) is a type of string
  description = null
  # enable_ave - (optional) is a type of string
  enable_ave = null
  # enable_tag - (optional) is a type of string
  enable_tag = null
  # encap_mode - (optional) is a type of string
  encap_mode = null
  # enf_pref - (optional) is a type of string
  enf_pref = null
  # ep_inventory_type - (optional) is a type of string
  ep_inventory_type = null
  # ep_ret_time - (optional) is a type of string
  ep_ret_time = null
  # hv_avail_monitor - (optional) is a type of string
  hv_avail_monitor = null
  # mcast_addr - (optional) is a type of string
  mcast_addr = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pref_encap_mode - (optional) is a type of string
  pref_encap_mode = null
  # provider_profile_dn - (required) is a type of string
  provider_profile_dn = null
  # relation_infra_rs_dom_vxlan_ns_def - (optional) is a type of string
  relation_infra_rs_dom_vxlan_ns_def = null
  # relation_infra_rs_vip_addr_ns - (optional) is a type of string
  relation_infra_rs_vip_addr_ns = null
  # relation_infra_rs_vlan_ns - (optional) is a type of string
  relation_infra_rs_vlan_ns = null
  # relation_infra_rs_vlan_ns_def - (optional) is a type of string
  relation_infra_rs_vlan_ns_def = null
  # relation_vmm_rs_default_cdp_if_pol - (optional) is a type of string
  relation_vmm_rs_default_cdp_if_pol = null
  # relation_vmm_rs_default_fw_pol - (optional) is a type of string
  relation_vmm_rs_default_fw_pol = null
  # relation_vmm_rs_default_l2_inst_pol - (optional) is a type of string
  relation_vmm_rs_default_l2_inst_pol = null
  # relation_vmm_rs_default_lacp_lag_pol - (optional) is a type of string
  relation_vmm_rs_default_lacp_lag_pol = null
  # relation_vmm_rs_default_lldp_if_pol - (optional) is a type of string
  relation_vmm_rs_default_lldp_if_pol = null
  # relation_vmm_rs_default_stp_if_pol - (optional) is a type of string
  relation_vmm_rs_default_stp_if_pol = null
  # relation_vmm_rs_dom_mcast_addr_ns - (optional) is a type of string
  relation_vmm_rs_dom_mcast_addr_ns = null
  # relation_vmm_rs_pref_enhanced_lag_pol - (optional) is a type of string
  relation_vmm_rs_pref_enhanced_lag_pol = null
}
```

[top](#index)

### Variables

```terraform
variable "access_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_learning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ave_time_out" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_infra_pg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ctrl_knob" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delimiter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_ave" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encap_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enf_pref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ep_inventory_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ep_ret_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hv_avail_monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mcast_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pref_encap_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_profile_dn" {
  description = "(required)"
  type        = string
}

variable "relation_infra_rs_dom_vxlan_ns_def" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_vip_addr_ns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_vlan_ns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_vlan_ns_def" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_default_cdp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_default_fw_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_default_l2_inst_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_default_lacp_lag_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_default_lldp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_default_stp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_dom_mcast_addr_ns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_vmm_rs_pref_enhanced_lag_pol" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_vmm_domain" "this" {
  # access_mode - (optional) is a type of string
  access_mode = var.access_mode
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # arp_learning - (optional) is a type of string
  arp_learning = var.arp_learning
  # ave_time_out - (optional) is a type of string
  ave_time_out = var.ave_time_out
  # config_infra_pg - (optional) is a type of string
  config_infra_pg = var.config_infra_pg
  # ctrl_knob - (optional) is a type of string
  ctrl_knob = var.ctrl_knob
  # delimiter - (optional) is a type of string
  delimiter = var.delimiter
  # description - (optional) is a type of string
  description = var.description
  # enable_ave - (optional) is a type of string
  enable_ave = var.enable_ave
  # enable_tag - (optional) is a type of string
  enable_tag = var.enable_tag
  # encap_mode - (optional) is a type of string
  encap_mode = var.encap_mode
  # enf_pref - (optional) is a type of string
  enf_pref = var.enf_pref
  # ep_inventory_type - (optional) is a type of string
  ep_inventory_type = var.ep_inventory_type
  # ep_ret_time - (optional) is a type of string
  ep_ret_time = var.ep_ret_time
  # hv_avail_monitor - (optional) is a type of string
  hv_avail_monitor = var.hv_avail_monitor
  # mcast_addr - (optional) is a type of string
  mcast_addr = var.mcast_addr
  # mode - (optional) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # pref_encap_mode - (optional) is a type of string
  pref_encap_mode = var.pref_encap_mode
  # provider_profile_dn - (required) is a type of string
  provider_profile_dn = var.provider_profile_dn
  # relation_infra_rs_dom_vxlan_ns_def - (optional) is a type of string
  relation_infra_rs_dom_vxlan_ns_def = var.relation_infra_rs_dom_vxlan_ns_def
  # relation_infra_rs_vip_addr_ns - (optional) is a type of string
  relation_infra_rs_vip_addr_ns = var.relation_infra_rs_vip_addr_ns
  # relation_infra_rs_vlan_ns - (optional) is a type of string
  relation_infra_rs_vlan_ns = var.relation_infra_rs_vlan_ns
  # relation_infra_rs_vlan_ns_def - (optional) is a type of string
  relation_infra_rs_vlan_ns_def = var.relation_infra_rs_vlan_ns_def
  # relation_vmm_rs_default_cdp_if_pol - (optional) is a type of string
  relation_vmm_rs_default_cdp_if_pol = var.relation_vmm_rs_default_cdp_if_pol
  # relation_vmm_rs_default_fw_pol - (optional) is a type of string
  relation_vmm_rs_default_fw_pol = var.relation_vmm_rs_default_fw_pol
  # relation_vmm_rs_default_l2_inst_pol - (optional) is a type of string
  relation_vmm_rs_default_l2_inst_pol = var.relation_vmm_rs_default_l2_inst_pol
  # relation_vmm_rs_default_lacp_lag_pol - (optional) is a type of string
  relation_vmm_rs_default_lacp_lag_pol = var.relation_vmm_rs_default_lacp_lag_pol
  # relation_vmm_rs_default_lldp_if_pol - (optional) is a type of string
  relation_vmm_rs_default_lldp_if_pol = var.relation_vmm_rs_default_lldp_if_pol
  # relation_vmm_rs_default_stp_if_pol - (optional) is a type of string
  relation_vmm_rs_default_stp_if_pol = var.relation_vmm_rs_default_stp_if_pol
  # relation_vmm_rs_dom_mcast_addr_ns - (optional) is a type of string
  relation_vmm_rs_dom_mcast_addr_ns = var.relation_vmm_rs_dom_mcast_addr_ns
  # relation_vmm_rs_pref_enhanced_lag_pol - (optional) is a type of string
  relation_vmm_rs_pref_enhanced_lag_pol = var.relation_vmm_rs_pref_enhanced_lag_pol
}
```

[top](#index)

### Outputs

```terraform
output "access_mode" {
  description = "returns a string"
  value       = aci_vmm_domain.this.access_mode
}

output "arp_learning" {
  description = "returns a string"
  value       = aci_vmm_domain.this.arp_learning
}

output "ave_time_out" {
  description = "returns a string"
  value       = aci_vmm_domain.this.ave_time_out
}

output "config_infra_pg" {
  description = "returns a string"
  value       = aci_vmm_domain.this.config_infra_pg
}

output "ctrl_knob" {
  description = "returns a string"
  value       = aci_vmm_domain.this.ctrl_knob
}

output "delimiter" {
  description = "returns a string"
  value       = aci_vmm_domain.this.delimiter
}

output "description" {
  description = "returns a string"
  value       = aci_vmm_domain.this.description
}

output "enable_ave" {
  description = "returns a string"
  value       = aci_vmm_domain.this.enable_ave
}

output "enable_tag" {
  description = "returns a string"
  value       = aci_vmm_domain.this.enable_tag
}

output "encap_mode" {
  description = "returns a string"
  value       = aci_vmm_domain.this.encap_mode
}

output "enf_pref" {
  description = "returns a string"
  value       = aci_vmm_domain.this.enf_pref
}

output "ep_inventory_type" {
  description = "returns a string"
  value       = aci_vmm_domain.this.ep_inventory_type
}

output "ep_ret_time" {
  description = "returns a string"
  value       = aci_vmm_domain.this.ep_ret_time
}

output "hv_avail_monitor" {
  description = "returns a string"
  value       = aci_vmm_domain.this.hv_avail_monitor
}

output "id" {
  description = "returns a string"
  value       = aci_vmm_domain.this.id
}

output "mcast_addr" {
  description = "returns a string"
  value       = aci_vmm_domain.this.mcast_addr
}

output "mode" {
  description = "returns a string"
  value       = aci_vmm_domain.this.mode
}

output "name_alias" {
  description = "returns a string"
  value       = aci_vmm_domain.this.name_alias
}

output "pref_encap_mode" {
  description = "returns a string"
  value       = aci_vmm_domain.this.pref_encap_mode
}

output "this" {
  value = aci_vmm_domain.this
}
```

[top](#index)