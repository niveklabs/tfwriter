# aci_leaf_access_port_policy_group

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
module "aci_leaf_access_port_policy_group" {
  source = "./modules/aci/r/aci_leaf_access_port_policy_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_infra_rs_att_ent_p - (optional) is a type of string
  relation_infra_rs_att_ent_p = null
  # relation_infra_rs_cdp_if_pol - (optional) is a type of string
  relation_infra_rs_cdp_if_pol = null
  # relation_infra_rs_copp_if_pol - (optional) is a type of string
  relation_infra_rs_copp_if_pol = null
  # relation_infra_rs_dwdm_if_pol - (optional) is a type of string
  relation_infra_rs_dwdm_if_pol = null
  # relation_infra_rs_fc_if_pol - (optional) is a type of string
  relation_infra_rs_fc_if_pol = null
  # relation_infra_rs_h_if_pol - (optional) is a type of string
  relation_infra_rs_h_if_pol = null
  # relation_infra_rs_l2_if_pol - (optional) is a type of string
  relation_infra_rs_l2_if_pol = null
  # relation_infra_rs_l2_inst_pol - (optional) is a type of string
  relation_infra_rs_l2_inst_pol = null
  # relation_infra_rs_l2_port_auth_pol - (optional) is a type of string
  relation_infra_rs_l2_port_auth_pol = null
  # relation_infra_rs_l2_port_security_pol - (optional) is a type of string
  relation_infra_rs_l2_port_security_pol = null
  # relation_infra_rs_lldp_if_pol - (optional) is a type of string
  relation_infra_rs_lldp_if_pol = null
  # relation_infra_rs_macsec_if_pol - (optional) is a type of string
  relation_infra_rs_macsec_if_pol = null
  # relation_infra_rs_mcp_if_pol - (optional) is a type of string
  relation_infra_rs_mcp_if_pol = null
  # relation_infra_rs_mon_if_infra_pol - (optional) is a type of string
  relation_infra_rs_mon_if_infra_pol = null
  # relation_infra_rs_poe_if_pol - (optional) is a type of string
  relation_infra_rs_poe_if_pol = null
  # relation_infra_rs_qos_dpp_if_pol - (optional) is a type of string
  relation_infra_rs_qos_dpp_if_pol = null
  # relation_infra_rs_qos_egress_dpp_if_pol - (optional) is a type of string
  relation_infra_rs_qos_egress_dpp_if_pol = null
  # relation_infra_rs_qos_ingress_dpp_if_pol - (optional) is a type of string
  relation_infra_rs_qos_ingress_dpp_if_pol = null
  # relation_infra_rs_qos_pfc_if_pol - (optional) is a type of string
  relation_infra_rs_qos_pfc_if_pol = null
  # relation_infra_rs_qos_sd_if_pol - (optional) is a type of string
  relation_infra_rs_qos_sd_if_pol = null
  # relation_infra_rs_span_v_dest_grp - (optional) is a type of set of string
  relation_infra_rs_span_v_dest_grp = []
  # relation_infra_rs_span_v_src_grp - (optional) is a type of set of string
  relation_infra_rs_span_v_src_grp = []
  # relation_infra_rs_stormctrl_if_pol - (optional) is a type of string
  relation_infra_rs_stormctrl_if_pol = null
  # relation_infra_rs_stp_if_pol - (optional) is a type of string
  relation_infra_rs_stp_if_pol = null

  relation_infra_rs_netflow_monitor_pol = [{
    flt_type                    = null
    tn_netflow_monitor_pol_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
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

variable "relation_infra_rs_att_ent_p" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_cdp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_copp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_dwdm_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_fc_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_h_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_l2_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_l2_inst_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_l2_port_auth_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_l2_port_security_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_lldp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_macsec_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_mcp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_mon_if_infra_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_poe_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_qos_dpp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_qos_egress_dpp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_qos_ingress_dpp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_qos_pfc_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_qos_sd_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_span_v_dest_grp" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_infra_rs_span_v_src_grp" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_infra_rs_stormctrl_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_stp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_netflow_monitor_pol" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      flt_type                    = string
      tn_netflow_monitor_pol_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aci_leaf_access_port_policy_group" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # relation_infra_rs_att_ent_p - (optional) is a type of string
  relation_infra_rs_att_ent_p = var.relation_infra_rs_att_ent_p
  # relation_infra_rs_cdp_if_pol - (optional) is a type of string
  relation_infra_rs_cdp_if_pol = var.relation_infra_rs_cdp_if_pol
  # relation_infra_rs_copp_if_pol - (optional) is a type of string
  relation_infra_rs_copp_if_pol = var.relation_infra_rs_copp_if_pol
  # relation_infra_rs_dwdm_if_pol - (optional) is a type of string
  relation_infra_rs_dwdm_if_pol = var.relation_infra_rs_dwdm_if_pol
  # relation_infra_rs_fc_if_pol - (optional) is a type of string
  relation_infra_rs_fc_if_pol = var.relation_infra_rs_fc_if_pol
  # relation_infra_rs_h_if_pol - (optional) is a type of string
  relation_infra_rs_h_if_pol = var.relation_infra_rs_h_if_pol
  # relation_infra_rs_l2_if_pol - (optional) is a type of string
  relation_infra_rs_l2_if_pol = var.relation_infra_rs_l2_if_pol
  # relation_infra_rs_l2_inst_pol - (optional) is a type of string
  relation_infra_rs_l2_inst_pol = var.relation_infra_rs_l2_inst_pol
  # relation_infra_rs_l2_port_auth_pol - (optional) is a type of string
  relation_infra_rs_l2_port_auth_pol = var.relation_infra_rs_l2_port_auth_pol
  # relation_infra_rs_l2_port_security_pol - (optional) is a type of string
  relation_infra_rs_l2_port_security_pol = var.relation_infra_rs_l2_port_security_pol
  # relation_infra_rs_lldp_if_pol - (optional) is a type of string
  relation_infra_rs_lldp_if_pol = var.relation_infra_rs_lldp_if_pol
  # relation_infra_rs_macsec_if_pol - (optional) is a type of string
  relation_infra_rs_macsec_if_pol = var.relation_infra_rs_macsec_if_pol
  # relation_infra_rs_mcp_if_pol - (optional) is a type of string
  relation_infra_rs_mcp_if_pol = var.relation_infra_rs_mcp_if_pol
  # relation_infra_rs_mon_if_infra_pol - (optional) is a type of string
  relation_infra_rs_mon_if_infra_pol = var.relation_infra_rs_mon_if_infra_pol
  # relation_infra_rs_poe_if_pol - (optional) is a type of string
  relation_infra_rs_poe_if_pol = var.relation_infra_rs_poe_if_pol
  # relation_infra_rs_qos_dpp_if_pol - (optional) is a type of string
  relation_infra_rs_qos_dpp_if_pol = var.relation_infra_rs_qos_dpp_if_pol
  # relation_infra_rs_qos_egress_dpp_if_pol - (optional) is a type of string
  relation_infra_rs_qos_egress_dpp_if_pol = var.relation_infra_rs_qos_egress_dpp_if_pol
  # relation_infra_rs_qos_ingress_dpp_if_pol - (optional) is a type of string
  relation_infra_rs_qos_ingress_dpp_if_pol = var.relation_infra_rs_qos_ingress_dpp_if_pol
  # relation_infra_rs_qos_pfc_if_pol - (optional) is a type of string
  relation_infra_rs_qos_pfc_if_pol = var.relation_infra_rs_qos_pfc_if_pol
  # relation_infra_rs_qos_sd_if_pol - (optional) is a type of string
  relation_infra_rs_qos_sd_if_pol = var.relation_infra_rs_qos_sd_if_pol
  # relation_infra_rs_span_v_dest_grp - (optional) is a type of set of string
  relation_infra_rs_span_v_dest_grp = var.relation_infra_rs_span_v_dest_grp
  # relation_infra_rs_span_v_src_grp - (optional) is a type of set of string
  relation_infra_rs_span_v_src_grp = var.relation_infra_rs_span_v_src_grp
  # relation_infra_rs_stormctrl_if_pol - (optional) is a type of string
  relation_infra_rs_stormctrl_if_pol = var.relation_infra_rs_stormctrl_if_pol
  # relation_infra_rs_stp_if_pol - (optional) is a type of string
  relation_infra_rs_stp_if_pol = var.relation_infra_rs_stp_if_pol

  dynamic "relation_infra_rs_netflow_monitor_pol" {
    for_each = var.relation_infra_rs_netflow_monitor_pol
    content {
      # flt_type - (required) is a type of string
      flt_type = relation_infra_rs_netflow_monitor_pol.value["flt_type"]
      # tn_netflow_monitor_pol_name - (required) is a type of string
      tn_netflow_monitor_pol_name = relation_infra_rs_netflow_monitor_pol.value["tn_netflow_monitor_pol_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_leaf_access_port_policy_group.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_leaf_access_port_policy_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_leaf_access_port_policy_group.this.name_alias
}

output "this" {
  value = aci_leaf_access_port_policy_group.this
}
```

[top](#index)