# aci_logical_interface_profile

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
module "aci_logical_interface_profile" {
  source = "./modules/aci/r/aci_logical_interface_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # logical_node_profile_dn - (required) is a type of string
  logical_node_profile_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # prio - (optional) is a type of string
  prio = null
  # relation_l3ext_rs_arp_if_pol - (optional) is a type of string
  relation_l3ext_rs_arp_if_pol = null
  # relation_l3ext_rs_egress_qos_dpp_pol - (optional) is a type of string
  relation_l3ext_rs_egress_qos_dpp_pol = null
  # relation_l3ext_rs_ingress_qos_dpp_pol - (optional) is a type of string
  relation_l3ext_rs_ingress_qos_dpp_pol = null
  # relation_l3ext_rs_l_if_p_cust_qos_pol - (optional) is a type of string
  relation_l3ext_rs_l_if_p_cust_qos_pol = null
  # relation_l3ext_rs_nd_if_pol - (optional) is a type of string
  relation_l3ext_rs_nd_if_pol = null
  # relation_l3ext_rs_path_l3_out_att - (optional) is a type of set of string
  relation_l3ext_rs_path_l3_out_att = []
  # tag - (optional) is a type of string
  tag = null

  relation_l3ext_rs_l_if_p_to_netflow_monitor_pol = [{
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

variable "logical_node_profile_dn" {
  description = "(required)"
  type        = string
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

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_arp_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_egress_qos_dpp_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_ingress_qos_dpp_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_l_if_p_cust_qos_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_nd_if_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_path_l3_out_att" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_l3ext_rs_l_if_p_to_netflow_monitor_pol" {
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
resource "aci_logical_interface_profile" "this" {
  annotation                            = var.annotation
  description                           = var.description
  logical_node_profile_dn               = var.logical_node_profile_dn
  name                                  = var.name
  name_alias                            = var.name_alias
  prio                                  = var.prio
  relation_l3ext_rs_arp_if_pol          = var.relation_l3ext_rs_arp_if_pol
  relation_l3ext_rs_egress_qos_dpp_pol  = var.relation_l3ext_rs_egress_qos_dpp_pol
  relation_l3ext_rs_ingress_qos_dpp_pol = var.relation_l3ext_rs_ingress_qos_dpp_pol
  relation_l3ext_rs_l_if_p_cust_qos_pol = var.relation_l3ext_rs_l_if_p_cust_qos_pol
  relation_l3ext_rs_nd_if_pol           = var.relation_l3ext_rs_nd_if_pol
  relation_l3ext_rs_path_l3_out_att     = var.relation_l3ext_rs_path_l3_out_att
  tag                                   = var.tag

  dynamic "relation_l3ext_rs_l_if_p_to_netflow_monitor_pol" {
    for_each = var.relation_l3ext_rs_l_if_p_to_netflow_monitor_pol
    content {
      # flt_type - (required) is a type of string
      flt_type = relation_l3ext_rs_l_if_p_to_netflow_monitor_pol.value["flt_type"]
      # tn_netflow_monitor_pol_name - (required) is a type of string
      tn_netflow_monitor_pol_name = relation_l3ext_rs_l_if_p_to_netflow_monitor_pol.value["tn_netflow_monitor_pol_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_logical_interface_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_logical_interface_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_logical_interface_profile.this.name_alias
}

output "prio" {
  description = "returns a string"
  value       = aci_logical_interface_profile.this.prio
}

output "tag" {
  description = "returns a string"
  value       = aci_logical_interface_profile.this.tag
}

output "this" {
  value = aci_logical_interface_profile.this
}
```

[top](#index)