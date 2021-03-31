# aci_vrf

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
module "aci_vrf" {
  source = "./modules/aci/r/aci_vrf"

  # annotation - (optional) is a type of string
  annotation = null
  # bd_enforced_enable - (optional) is a type of string
  bd_enforced_enable = null
  # description - (optional) is a type of string
  description = null
  # ip_data_plane_learning - (optional) is a type of string
  ip_data_plane_learning = null
  # knw_mcast_act - (optional) is a type of string
  knw_mcast_act = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pc_enf_dir - (optional) is a type of string
  pc_enf_dir = null
  # pc_enf_pref - (optional) is a type of string
  pc_enf_pref = null
  # relation_fv_rs_bgp_ctx_pol - (optional) is a type of string
  relation_fv_rs_bgp_ctx_pol = null
  # relation_fv_rs_ctx_mcast_to - (optional) is a type of set of string
  relation_fv_rs_ctx_mcast_to = []
  # relation_fv_rs_ctx_mon_pol - (optional) is a type of string
  relation_fv_rs_ctx_mon_pol = null
  # relation_fv_rs_ctx_to_ep_ret - (optional) is a type of string
  relation_fv_rs_ctx_to_ep_ret = null
  # relation_fv_rs_ctx_to_ext_route_tag_pol - (optional) is a type of string
  relation_fv_rs_ctx_to_ext_route_tag_pol = null
  # relation_fv_rs_ospf_ctx_pol - (optional) is a type of string
  relation_fv_rs_ospf_ctx_pol = null
  # relation_fv_rs_vrf_validation_pol - (optional) is a type of string
  relation_fv_rs_vrf_validation_pol = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null

  relation_fv_rs_ctx_to_bgp_ctx_af_pol = [{
    af                     = null
    tn_bgp_ctx_af_pol_name = null
  }]

  relation_fv_rs_ctx_to_eigrp_ctx_af_pol = [{
    af                       = null
    tn_eigrp_ctx_af_pol_name = null
  }]

  relation_fv_rs_ctx_to_ospf_ctx_pol = [{
    af                   = null
    tn_ospf_ctx_pol_name = null
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

variable "bd_enforced_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_data_plane_learning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "knw_mcast_act" {
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

variable "pc_enf_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pc_enf_pref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bgp_ctx_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_ctx_mcast_to" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_ctx_mon_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_ctx_to_ep_ret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_ctx_to_ext_route_tag_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_ospf_ctx_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_vrf_validation_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "relation_fv_rs_ctx_to_bgp_ctx_af_pol" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      af                     = string
      tn_bgp_ctx_af_pol_name = string
    }
  ))
  default = []
}

variable "relation_fv_rs_ctx_to_eigrp_ctx_af_pol" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      af                       = string
      tn_eigrp_ctx_af_pol_name = string
    }
  ))
  default = []
}

variable "relation_fv_rs_ctx_to_ospf_ctx_pol" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      af                   = string
      tn_ospf_ctx_pol_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aci_vrf" "this" {
  annotation                              = var.annotation
  bd_enforced_enable                      = var.bd_enforced_enable
  description                             = var.description
  ip_data_plane_learning                  = var.ip_data_plane_learning
  knw_mcast_act                           = var.knw_mcast_act
  name                                    = var.name
  name_alias                              = var.name_alias
  pc_enf_dir                              = var.pc_enf_dir
  pc_enf_pref                             = var.pc_enf_pref
  relation_fv_rs_bgp_ctx_pol              = var.relation_fv_rs_bgp_ctx_pol
  relation_fv_rs_ctx_mcast_to             = var.relation_fv_rs_ctx_mcast_to
  relation_fv_rs_ctx_mon_pol              = var.relation_fv_rs_ctx_mon_pol
  relation_fv_rs_ctx_to_ep_ret            = var.relation_fv_rs_ctx_to_ep_ret
  relation_fv_rs_ctx_to_ext_route_tag_pol = var.relation_fv_rs_ctx_to_ext_route_tag_pol
  relation_fv_rs_ospf_ctx_pol             = var.relation_fv_rs_ospf_ctx_pol
  relation_fv_rs_vrf_validation_pol       = var.relation_fv_rs_vrf_validation_pol
  tenant_dn                               = var.tenant_dn

  dynamic "relation_fv_rs_ctx_to_bgp_ctx_af_pol" {
    for_each = var.relation_fv_rs_ctx_to_bgp_ctx_af_pol
    content {
      af                     = relation_fv_rs_ctx_to_bgp_ctx_af_pol.value["af"]
      tn_bgp_ctx_af_pol_name = relation_fv_rs_ctx_to_bgp_ctx_af_pol.value["tn_bgp_ctx_af_pol_name"]
    }
  }

  dynamic "relation_fv_rs_ctx_to_eigrp_ctx_af_pol" {
    for_each = var.relation_fv_rs_ctx_to_eigrp_ctx_af_pol
    content {
      af                       = relation_fv_rs_ctx_to_eigrp_ctx_af_pol.value["af"]
      tn_eigrp_ctx_af_pol_name = relation_fv_rs_ctx_to_eigrp_ctx_af_pol.value["tn_eigrp_ctx_af_pol_name"]
    }
  }

  dynamic "relation_fv_rs_ctx_to_ospf_ctx_pol" {
    for_each = var.relation_fv_rs_ctx_to_ospf_ctx_pol
    content {
      af                   = relation_fv_rs_ctx_to_ospf_ctx_pol.value["af"]
      tn_ospf_ctx_pol_name = relation_fv_rs_ctx_to_ospf_ctx_pol.value["tn_ospf_ctx_pol_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bd_enforced_enable" {
  description = "returns a string"
  value       = aci_vrf.this.bd_enforced_enable
}

output "description" {
  description = "returns a string"
  value       = aci_vrf.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_vrf.this.id
}

output "ip_data_plane_learning" {
  description = "returns a string"
  value       = aci_vrf.this.ip_data_plane_learning
}

output "knw_mcast_act" {
  description = "returns a string"
  value       = aci_vrf.this.knw_mcast_act
}

output "name_alias" {
  description = "returns a string"
  value       = aci_vrf.this.name_alias
}

output "pc_enf_dir" {
  description = "returns a string"
  value       = aci_vrf.this.pc_enf_dir
}

output "pc_enf_pref" {
  description = "returns a string"
  value       = aci_vrf.this.pc_enf_pref
}

output "this" {
  value = aci_vrf.this
}
```

[top](#index)