# nsxt_policy_tier1_gateway

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_tier1_gateway" {
  source = "./modules/nsxt/r/nsxt_policy_tier1_gateway"

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
  # egress_qos_profile_path - (optional) is a type of string
  egress_qos_profile_path = null
  # enable_firewall - (optional) is a type of bool
  enable_firewall = null
  # enable_standby_relocation - (optional) is a type of bool
  enable_standby_relocation = null
  # failover_mode - (optional) is a type of string
  failover_mode = null
  # force_whitelisting - (optional) is a type of bool
  force_whitelisting = null
  # ingress_qos_profile_path - (optional) is a type of string
  ingress_qos_profile_path = null
  # ipv6_dad_profile_path - (optional) is a type of string
  ipv6_dad_profile_path = null
  # ipv6_ndra_profile_path - (optional) is a type of string
  ipv6_ndra_profile_path = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # pool_allocation - (optional) is a type of string
  pool_allocation = null
  # route_advertisement_types - (optional) is a type of set of string
  route_advertisement_types = []
  # tier0_path - (optional) is a type of string
  tier0_path = null

  intersite_config = [{
    fallback_site_paths = []
    primary_site_path   = null
    transit_subnet      = null
  }]

  locale_service = [{
    edge_cluster_path    = null
    path                 = null
    preferred_edge_paths = []
    revision             = null
  }]

  route_advertisement_rule = [{
    action                    = null
    name                      = null
    prefix_operator           = null
    route_advertisement_types = []
    subnets                   = []
  }]

  tag = [{
    scope = null
    tag   = null
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
  description = "(optional) - Policy path to DHCP server or relay configuration to use for this Tier1"
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

variable "egress_qos_profile_path" {
  description = "(optional) - Policy path to gateway QoS profile in egress direction"
  type        = string
  default     = null
}

variable "enable_firewall" {
  description = "(optional) - Enable edge firewall"
  type        = bool
  default     = null
}

variable "enable_standby_relocation" {
  description = "(optional) - Enable standby relocation"
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

variable "ingress_qos_profile_path" {
  description = "(optional) - Policy path to gateway QoS profile in ingress direction"
  type        = string
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

variable "pool_allocation" {
  description = "(optional) - Edge node allocation at different sizes for routing and load balancer service to meet performance and scalability requirements"
  type        = string
  default     = null
}

variable "route_advertisement_types" {
  description = "(optional) - Enable different types of route advertisements"
  type        = set(string)
  default     = null
}

variable "tier0_path" {
  description = "(optional) - The path of the connected Tier0"
  type        = string
  default     = null
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
      revision             = number
    }
  ))
  default = []
}

variable "route_advertisement_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action                    = string
      name                      = string
      prefix_operator           = string
      route_advertisement_types = set(string)
      subnets                   = set(string)
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
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_tier1_gateway" "this" {
  # default_rule_logging - (optional) is a type of bool
  default_rule_logging = var.default_rule_logging
  # description - (optional) is a type of string
  description = var.description
  # dhcp_config_path - (optional) is a type of string
  dhcp_config_path = var.dhcp_config_path
  # display_name - (required) is a type of string
  display_name = var.display_name
  # edge_cluster_path - (optional) is a type of string
  edge_cluster_path = var.edge_cluster_path
  # egress_qos_profile_path - (optional) is a type of string
  egress_qos_profile_path = var.egress_qos_profile_path
  # enable_firewall - (optional) is a type of bool
  enable_firewall = var.enable_firewall
  # enable_standby_relocation - (optional) is a type of bool
  enable_standby_relocation = var.enable_standby_relocation
  # failover_mode - (optional) is a type of string
  failover_mode = var.failover_mode
  # force_whitelisting - (optional) is a type of bool
  force_whitelisting = var.force_whitelisting
  # ingress_qos_profile_path - (optional) is a type of string
  ingress_qos_profile_path = var.ingress_qos_profile_path
  # ipv6_dad_profile_path - (optional) is a type of string
  ipv6_dad_profile_path = var.ipv6_dad_profile_path
  # ipv6_ndra_profile_path - (optional) is a type of string
  ipv6_ndra_profile_path = var.ipv6_ndra_profile_path
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # pool_allocation - (optional) is a type of string
  pool_allocation = var.pool_allocation
  # route_advertisement_types - (optional) is a type of set of string
  route_advertisement_types = var.route_advertisement_types
  # tier0_path - (optional) is a type of string
  tier0_path = var.tier0_path

  dynamic "intersite_config" {
    for_each = var.intersite_config
    content {
      # fallback_site_paths - (optional) is a type of set of string
      fallback_site_paths = intersite_config.value["fallback_site_paths"]
      # primary_site_path - (optional) is a type of string
      primary_site_path = intersite_config.value["primary_site_path"]
      # transit_subnet - (optional) is a type of string
      transit_subnet = intersite_config.value["transit_subnet"]
    }
  }

  dynamic "locale_service" {
    for_each = var.locale_service
    content {
      # edge_cluster_path - (required) is a type of string
      edge_cluster_path = locale_service.value["edge_cluster_path"]
      # preferred_edge_paths - (optional) is a type of set of string
      preferred_edge_paths = locale_service.value["preferred_edge_paths"]
    }
  }

  dynamic "route_advertisement_rule" {
    for_each = var.route_advertisement_rule
    content {
      # action - (optional) is a type of string
      action = route_advertisement_rule.value["action"]
      # name - (required) is a type of string
      name = route_advertisement_rule.value["name"]
      # prefix_operator - (optional) is a type of string
      prefix_operator = route_advertisement_rule.value["prefix_operator"]
      # route_advertisement_types - (optional) is a type of set of string
      route_advertisement_types = route_advertisement_rule.value["route_advertisement_types"]
      # subnets - (required) is a type of set of string
      subnets = route_advertisement_rule.value["subnets"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "edge_cluster_path" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway.this.edge_cluster_path
}

output "id" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway.this.id
}

output "ipv6_dad_profile_path" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway.this.ipv6_dad_profile_path
}

output "ipv6_ndra_profile_path" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway.this.ipv6_ndra_profile_path
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_tier1_gateway.this.revision
}

output "this" {
  value = nsxt_policy_tier1_gateway.this
}
```

[top](#index)