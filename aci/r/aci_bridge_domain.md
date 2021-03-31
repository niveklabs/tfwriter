# aci_bridge_domain

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
module "aci_bridge_domain" {
  source = "./modules/aci/r/aci_bridge_domain"

  # annotation - (optional) is a type of string
  annotation = null
  # arp_flood - (optional) is a type of string
  arp_flood = null
  # bridge_domain_type - (optional) is a type of string
  bridge_domain_type = null
  # description - (optional) is a type of string
  description = null
  # ep_clear - (optional) is a type of string
  ep_clear = null
  # ep_move_detect_mode - (optional) is a type of string
  ep_move_detect_mode = null
  # host_based_routing - (optional) is a type of string
  host_based_routing = null
  # intersite_bum_traffic_allow - (optional) is a type of string
  intersite_bum_traffic_allow = null
  # intersite_l2_stretch - (optional) is a type of string
  intersite_l2_stretch = null
  # ip_learning - (optional) is a type of string
  ip_learning = null
  # ipv6_mcast_allow - (optional) is a type of string
  ipv6_mcast_allow = null
  # limit_ip_learn_to_subnets - (optional) is a type of string
  limit_ip_learn_to_subnets = null
  # ll_addr - (optional) is a type of string
  ll_addr = null
  # mac - (optional) is a type of string
  mac = null
  # mcast_allow - (optional) is a type of string
  mcast_allow = null
  # multi_dst_pkt_act - (optional) is a type of string
  multi_dst_pkt_act = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # optimize_wan_bandwidth - (optional) is a type of string
  optimize_wan_bandwidth = null
  # relation_fv_rs_abd_pol_mon_pol - (optional) is a type of string
  relation_fv_rs_abd_pol_mon_pol = null
  # relation_fv_rs_bd_flood_to - (optional) is a type of set of string
  relation_fv_rs_bd_flood_to = []
  # relation_fv_rs_bd_to_ep_ret - (optional) is a type of string
  relation_fv_rs_bd_to_ep_ret = null
  # relation_fv_rs_bd_to_fhs - (optional) is a type of string
  relation_fv_rs_bd_to_fhs = null
  # relation_fv_rs_bd_to_nd_p - (optional) is a type of string
  relation_fv_rs_bd_to_nd_p = null
  # relation_fv_rs_bd_to_out - (optional) is a type of set of string
  relation_fv_rs_bd_to_out = []
  # relation_fv_rs_bd_to_profile - (optional) is a type of string
  relation_fv_rs_bd_to_profile = null
  # relation_fv_rs_bd_to_relay_p - (optional) is a type of string
  relation_fv_rs_bd_to_relay_p = null
  # relation_fv_rs_ctx - (optional) is a type of string
  relation_fv_rs_ctx = null
  # relation_fv_rs_igmpsn - (optional) is a type of string
  relation_fv_rs_igmpsn = null
  # relation_fv_rs_mldsn - (optional) is a type of string
  relation_fv_rs_mldsn = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
  # unicast_route - (optional) is a type of string
  unicast_route = null
  # unk_mac_ucast_act - (optional) is a type of string
  unk_mac_ucast_act = null
  # unk_mcast_act - (optional) is a type of string
  unk_mcast_act = null
  # v6unk_mcast_act - (optional) is a type of string
  v6unk_mcast_act = null
  # vmac - (optional) is a type of string
  vmac = null

  relation_fv_rs_bd_to_netflow_monitor_pol = [{
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

variable "arp_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bridge_domain_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ep_clear" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ep_move_detect_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_based_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intersite_bum_traffic_allow" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intersite_l2_stretch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_learning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_mcast_allow" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "limit_ip_learn_to_subnets" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ll_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mcast_allow" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi_dst_pkt_act" {
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

variable "optimize_wan_bandwidth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_abd_pol_mon_pol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_flood_to" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_bd_to_ep_ret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_to_fhs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_to_nd_p" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_to_out" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "relation_fv_rs_bd_to_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_to_relay_p" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_ctx" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_igmpsn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_mldsn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "unicast_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unk_mac_ucast_act" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unk_mcast_act" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "v6unk_mcast_act" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vmac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_fv_rs_bd_to_netflow_monitor_pol" {
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
resource "aci_bridge_domain" "this" {
  annotation                     = var.annotation
  arp_flood                      = var.arp_flood
  bridge_domain_type             = var.bridge_domain_type
  description                    = var.description
  ep_clear                       = var.ep_clear
  ep_move_detect_mode            = var.ep_move_detect_mode
  host_based_routing             = var.host_based_routing
  intersite_bum_traffic_allow    = var.intersite_bum_traffic_allow
  intersite_l2_stretch           = var.intersite_l2_stretch
  ip_learning                    = var.ip_learning
  ipv6_mcast_allow               = var.ipv6_mcast_allow
  limit_ip_learn_to_subnets      = var.limit_ip_learn_to_subnets
  ll_addr                        = var.ll_addr
  mac                            = var.mac
  mcast_allow                    = var.mcast_allow
  multi_dst_pkt_act              = var.multi_dst_pkt_act
  name                           = var.name
  name_alias                     = var.name_alias
  optimize_wan_bandwidth         = var.optimize_wan_bandwidth
  relation_fv_rs_abd_pol_mon_pol = var.relation_fv_rs_abd_pol_mon_pol
  relation_fv_rs_bd_flood_to     = var.relation_fv_rs_bd_flood_to
  relation_fv_rs_bd_to_ep_ret    = var.relation_fv_rs_bd_to_ep_ret
  relation_fv_rs_bd_to_fhs       = var.relation_fv_rs_bd_to_fhs
  relation_fv_rs_bd_to_nd_p      = var.relation_fv_rs_bd_to_nd_p
  relation_fv_rs_bd_to_out       = var.relation_fv_rs_bd_to_out
  relation_fv_rs_bd_to_profile   = var.relation_fv_rs_bd_to_profile
  relation_fv_rs_bd_to_relay_p   = var.relation_fv_rs_bd_to_relay_p
  relation_fv_rs_ctx             = var.relation_fv_rs_ctx
  relation_fv_rs_igmpsn          = var.relation_fv_rs_igmpsn
  relation_fv_rs_mldsn           = var.relation_fv_rs_mldsn
  tenant_dn                      = var.tenant_dn
  unicast_route                  = var.unicast_route
  unk_mac_ucast_act              = var.unk_mac_ucast_act
  unk_mcast_act                  = var.unk_mcast_act
  v6unk_mcast_act                = var.v6unk_mcast_act
  vmac                           = var.vmac

  dynamic "relation_fv_rs_bd_to_netflow_monitor_pol" {
    for_each = var.relation_fv_rs_bd_to_netflow_monitor_pol
    content {
      flt_type                    = relation_fv_rs_bd_to_netflow_monitor_pol.value["flt_type"]
      tn_netflow_monitor_pol_name = relation_fv_rs_bd_to_netflow_monitor_pol.value["tn_netflow_monitor_pol_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arp_flood" {
  description = "returns a string"
  value       = aci_bridge_domain.this.arp_flood
}

output "bridge_domain_type" {
  description = "returns a string"
  value       = aci_bridge_domain.this.bridge_domain_type
}

output "description" {
  description = "returns a string"
  value       = aci_bridge_domain.this.description
}

output "ep_clear" {
  description = "returns a string"
  value       = aci_bridge_domain.this.ep_clear
}

output "ep_move_detect_mode" {
  description = "returns a string"
  value       = aci_bridge_domain.this.ep_move_detect_mode
}

output "host_based_routing" {
  description = "returns a string"
  value       = aci_bridge_domain.this.host_based_routing
}

output "id" {
  description = "returns a string"
  value       = aci_bridge_domain.this.id
}

output "intersite_bum_traffic_allow" {
  description = "returns a string"
  value       = aci_bridge_domain.this.intersite_bum_traffic_allow
}

output "intersite_l2_stretch" {
  description = "returns a string"
  value       = aci_bridge_domain.this.intersite_l2_stretch
}

output "ip_learning" {
  description = "returns a string"
  value       = aci_bridge_domain.this.ip_learning
}

output "ipv6_mcast_allow" {
  description = "returns a string"
  value       = aci_bridge_domain.this.ipv6_mcast_allow
}

output "limit_ip_learn_to_subnets" {
  description = "returns a string"
  value       = aci_bridge_domain.this.limit_ip_learn_to_subnets
}

output "ll_addr" {
  description = "returns a string"
  value       = aci_bridge_domain.this.ll_addr
}

output "mac" {
  description = "returns a string"
  value       = aci_bridge_domain.this.mac
}

output "mcast_allow" {
  description = "returns a string"
  value       = aci_bridge_domain.this.mcast_allow
}

output "multi_dst_pkt_act" {
  description = "returns a string"
  value       = aci_bridge_domain.this.multi_dst_pkt_act
}

output "name_alias" {
  description = "returns a string"
  value       = aci_bridge_domain.this.name_alias
}

output "optimize_wan_bandwidth" {
  description = "returns a string"
  value       = aci_bridge_domain.this.optimize_wan_bandwidth
}

output "unicast_route" {
  description = "returns a string"
  value       = aci_bridge_domain.this.unicast_route
}

output "unk_mac_ucast_act" {
  description = "returns a string"
  value       = aci_bridge_domain.this.unk_mac_ucast_act
}

output "unk_mcast_act" {
  description = "returns a string"
  value       = aci_bridge_domain.this.unk_mcast_act
}

output "v6unk_mcast_act" {
  description = "returns a string"
  value       = aci_bridge_domain.this.v6unk_mcast_act
}

output "vmac" {
  description = "returns a string"
  value       = aci_bridge_domain.this.vmac
}

output "this" {
  value = aci_bridge_domain.this
}
```

[top](#index)