# nsxt_policy_tier0_gateway

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_tier0_gateway" {
  source = "./modules/nsxt/r/nsxt_policy_tier0_gateway"

  # default_rule_logging - (optional) is a type of bool
  default_rule_logging = null
  # description - (optional) is a type of string
  description = null
  # dhcp_config_path - (optional) is a type of string
  dhcp_config_path = null
  # display_name - (required) is a type of string
  display_name = null
  # edge_cluster_path - (optional) is a type of string
  edge_cluster_path = null
  # enable_firewall - (optional) is a type of bool
  enable_firewall = null
  # failover_mode - (optional) is a type of string
  failover_mode = null
  # force_whitelisting - (optional) is a type of bool
  force_whitelisting = null
  # ha_mode - (optional) is a type of string
  ha_mode = null
  # internal_transit_subnets - (optional) is a type of list of string
  internal_transit_subnets = []
  # ipv6_dad_profile_path - (optional) is a type of string
  ipv6_dad_profile_path = null
  # ipv6_ndra_profile_path - (optional) is a type of string
  ipv6_ndra_profile_path = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # transit_subnets - (optional) is a type of list of string
  transit_subnets = []

  bgp_config = [{
    ecmp                               = null
    enabled                            = null
    graceful_restart_mode              = null
    graceful_restart_stale_route_timer = null
    graceful_restart_timer             = null
    inter_sr_ibgp                      = null
    local_as_num                       = null
    multipath_relax                    = null
    path                               = null
    revision                           = null
    route_aggregation = [{
      prefix       = null
      summary_only = null
    }]
    tag = [{
      scope = null
      tag   = null
    }]
  }]

  intersite_config = [{
    fallback_site_paths = []
    primary_site_path   = null
    transit_subnet      = null
  }]

  locale_service = [{
    edge_cluster_path    = null
    path                 = null
    preferred_edge_paths = []
    redistribution_config = [{
      enabled = null
      rule = [{
        name           = null
        route_map_path = null
        types          = []
      }]
    }]
    revision = null
  }]

  redistribution_config = [{
    enabled = null
    rule = [{
      name           = null
      route_map_path = null
      types          = []
    }]
  }]

  tag = [{
    scope = null
    tag   = null
  }]

  vrf_config = [{
    evpn_transit_vni    = null
    gateway_path        = null
    path                = null
    route_distinguisher = null
    route_target = [{
      address_family = null
      auto_mode      = null
      export_targets = []
      import_targets = []
    }]
    tag = [{
      scope = null
      tag   = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_rule_logging" {
  description = "(optional) - Default rule logging"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "dhcp_config_path" {
  description = "(optional) - Policy path to DHCP server or relay configuration to use for this Tier0"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "edge_cluster_path" {
  description = "(optional) - The path of the edge cluster connected to this gateway"
  type        = string
  default     = null
}

variable "enable_firewall" {
  description = "(optional) - Enable edge firewall"
  type        = bool
  default     = null
}

variable "failover_mode" {
  description = "(optional) - Failover mode"
  type        = string
  default     = null
}

variable "force_whitelisting" {
  description = "(optional) - Force whitelisting"
  type        = bool
  default     = null
}

variable "ha_mode" {
  description = "(optional) - High-availability Mode for Tier-0"
  type        = string
  default     = null
}

variable "internal_transit_subnets" {
  description = "(optional) - Internal transit subnets in CIDR format"
  type        = list(string)
  default     = null
}

variable "ipv6_dad_profile_path" {
  description = "(optional) - The path of an IPv6 DAD profile"
  type        = string
  default     = null
}

variable "ipv6_ndra_profile_path" {
  description = "(optional) - The path of an IPv6 NDRA profile"
  type        = string
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "transit_subnets" {
  description = "(optional) - Transit subnets in CIDR format"
  type        = list(string)
  default     = null
}

variable "bgp_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ecmp                               = bool
      enabled                            = bool
      graceful_restart_mode              = string
      graceful_restart_stale_route_timer = number
      graceful_restart_timer             = number
      inter_sr_ibgp                      = bool
      local_as_num                       = string
      multipath_relax                    = bool
      path                               = string
      revision                           = number
      route_aggregation = list(object(
        {
          prefix       = string
          summary_only = bool
        }
      ))
      tag = set(object(
        {
          scope = string
          tag   = string
        }
      ))
    }
  ))
  default = []
}

variable "intersite_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fallback_site_paths = set(string)
      primary_site_path   = string
      transit_subnet      = string
    }
  ))
  default = []
}

variable "locale_service" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      edge_cluster_path    = string
      path                 = string
      preferred_edge_paths = set(string)
      redistribution_config = list(object(
        {
          enabled = bool
          rule = list(object(
            {
              name           = string
              route_map_path = string
              types          = set(string)
            }
          ))
        }
      ))
      revision = number
    }
  ))
  default = []
}

variable "redistribution_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      rule = list(object(
        {
          name           = string
          route_map_path = string
          types          = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}

variable "vrf_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      evpn_transit_vni    = number
      gateway_path        = string
      path                = string
      route_distinguisher = string
      route_target = list(object(
        {
          address_family = string
          auto_mode      = bool
          export_targets = list(string)
          import_targets = list(string)
        }
      ))
      tag = set(object(
        {
          scope = string
          tag   = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_tier0_gateway" "this" {
  default_rule_logging     = var.default_rule_logging
  description              = var.description
  dhcp_config_path         = var.dhcp_config_path
  display_name             = var.display_name
  edge_cluster_path        = var.edge_cluster_path
  enable_firewall          = var.enable_firewall
  failover_mode            = var.failover_mode
  force_whitelisting       = var.force_whitelisting
  ha_mode                  = var.ha_mode
  internal_transit_subnets = var.internal_transit_subnets
  ipv6_dad_profile_path    = var.ipv6_dad_profile_path
  ipv6_ndra_profile_path   = var.ipv6_ndra_profile_path
  nsx_id                   = var.nsx_id
  transit_subnets          = var.transit_subnets

  dynamic "bgp_config" {
    for_each = var.bgp_config
    content {
      ecmp                               = bgp_config.value["ecmp"]
      enabled                            = bgp_config.value["enabled"]
      graceful_restart_mode              = bgp_config.value["graceful_restart_mode"]
      graceful_restart_stale_route_timer = bgp_config.value["graceful_restart_stale_route_timer"]
      graceful_restart_timer             = bgp_config.value["graceful_restart_timer"]
      inter_sr_ibgp                      = bgp_config.value["inter_sr_ibgp"]
      local_as_num                       = bgp_config.value["local_as_num"]
      multipath_relax                    = bgp_config.value["multipath_relax"]

      dynamic "route_aggregation" {
        for_each = bgp_config.value.route_aggregation
        content {
          prefix       = route_aggregation.value["prefix"]
          summary_only = route_aggregation.value["summary_only"]
        }
      }

      dynamic "tag" {
        for_each = bgp_config.value.tag
        content {
          scope = tag.value["scope"]
          tag   = tag.value["tag"]
        }
      }

    }
  }

  dynamic "intersite_config" {
    for_each = var.intersite_config
    content {
      fallback_site_paths = intersite_config.value["fallback_site_paths"]
      primary_site_path   = intersite_config.value["primary_site_path"]
      transit_subnet      = intersite_config.value["transit_subnet"]
    }
  }

  dynamic "locale_service" {
    for_each = var.locale_service
    content {
      edge_cluster_path    = locale_service.value["edge_cluster_path"]
      preferred_edge_paths = locale_service.value["preferred_edge_paths"]

      dynamic "redistribution_config" {
        for_each = locale_service.value.redistribution_config
        content {
          enabled = redistribution_config.value["enabled"]

          dynamic "rule" {
            for_each = redistribution_config.value.rule
            content {
              name           = rule.value["name"]
              route_map_path = rule.value["route_map_path"]
              types          = rule.value["types"]
            }
          }

        }
      }

    }
  }

  dynamic "redistribution_config" {
    for_each = var.redistribution_config
    content {
      enabled = redistribution_config.value["enabled"]

      dynamic "rule" {
        for_each = redistribution_config.value.rule
        content {
          name           = rule.value["name"]
          route_map_path = rule.value["route_map_path"]
          types          = rule.value["types"]
        }
      }

    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

  dynamic "vrf_config" {
    for_each = var.vrf_config
    content {
      evpn_transit_vni    = vrf_config.value["evpn_transit_vni"]
      gateway_path        = vrf_config.value["gateway_path"]
      route_distinguisher = vrf_config.value["route_distinguisher"]

      dynamic "route_target" {
        for_each = vrf_config.value.route_target
        content {
          address_family = route_target.value["address_family"]
          auto_mode      = route_target.value["auto_mode"]
          export_targets = route_target.value["export_targets"]
          import_targets = route_target.value["import_targets"]
        }
      }

      dynamic "tag" {
        for_each = vrf_config.value.tag
        content {
          scope = tag.value["scope"]
          tag   = tag.value["tag"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "edge_cluster_path" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway.this.edge_cluster_path
}

output "id" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway.this.id
}

output "internal_transit_subnets" {
  description = "returns a list of string"
  value       = nsxt_policy_tier0_gateway.this.internal_transit_subnets
}

output "ipv6_dad_profile_path" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway.this.ipv6_dad_profile_path
}

output "ipv6_ndra_profile_path" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway.this.ipv6_ndra_profile_path
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_tier0_gateway.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_tier0_gateway.this.revision
}

output "transit_subnets" {
  description = "returns a list of string"
  value       = nsxt_policy_tier0_gateway.this.transit_subnets
}

output "this" {
  value = nsxt_policy_tier0_gateway.this
}
```

[top](#index)