# fortios_router_routemap

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_router_routemap" {
  source = "./modules/fortios/r/fortios_router_routemap"

  # comments - (optional) is a type of string
  comments = null
  # name - (required) is a type of string
  name = null

  rule = [{
    action                = null
    id                    = null
    match_as_path         = null
    match_community       = null
    match_community_exact = null
    match_flags           = null
    match_interface       = null
    match_ip6_address     = null
    match_ip6_nexthop     = null
    match_ip_address      = null
    match_ip_nexthop      = null
    match_metric          = null
    match_origin          = null
    match_route_type      = null
    match_tag             = null
    set_aggregator_as     = null
    set_aggregator_ip     = null
    set_aspath = [{
      as = null
    }]
    set_aspath_action    = null
    set_atomic_aggregate = null
    set_community = [{
      community = null
    }]
    set_community_additive                 = null
    set_community_delete                   = null
    set_dampening_max_suppress             = null
    set_dampening_reachability_half_life   = null
    set_dampening_reuse                    = null
    set_dampening_suppress                 = null
    set_dampening_unreachability_half_life = null
    set_extcommunity_rt = [{
      community = null
    }]
    set_extcommunity_soo = [{
      community = null
    }]
    set_flags             = null
    set_ip6_nexthop       = null
    set_ip6_nexthop_local = null
    set_ip_nexthop        = null
    set_local_preference  = null
    set_metric            = null
    set_metric_type       = null
    set_origin            = null
    set_originator_id     = null
    set_route_tag         = null
    set_tag               = null
    set_weight            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action                = string
      id                    = number
      match_as_path         = string
      match_community       = string
      match_community_exact = string
      match_flags           = number
      match_interface       = string
      match_ip6_address     = string
      match_ip6_nexthop     = string
      match_ip_address      = string
      match_ip_nexthop      = string
      match_metric          = number
      match_origin          = string
      match_route_type      = string
      match_tag             = number
      set_aggregator_as     = number
      set_aggregator_ip     = string
      set_aspath = list(object(
        {
          as = string
        }
      ))
      set_aspath_action    = string
      set_atomic_aggregate = string
      set_community = list(object(
        {
          community = string
        }
      ))
      set_community_additive                 = string
      set_community_delete                   = string
      set_dampening_max_suppress             = number
      set_dampening_reachability_half_life   = number
      set_dampening_reuse                    = number
      set_dampening_suppress                 = number
      set_dampening_unreachability_half_life = number
      set_extcommunity_rt = list(object(
        {
          community = string
        }
      ))
      set_extcommunity_soo = list(object(
        {
          community = string
        }
      ))
      set_flags             = number
      set_ip6_nexthop       = string
      set_ip6_nexthop_local = string
      set_ip_nexthop        = string
      set_local_preference  = number
      set_metric            = number
      set_metric_type       = string
      set_origin            = string
      set_originator_id     = string
      set_route_tag         = number
      set_tag               = number
      set_weight            = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_routemap" "this" {
  comments = var.comments
  name     = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      action                                 = rule.value["action"]
      id                                     = rule.value["id"]
      match_as_path                          = rule.value["match_as_path"]
      match_community                        = rule.value["match_community"]
      match_community_exact                  = rule.value["match_community_exact"]
      match_flags                            = rule.value["match_flags"]
      match_interface                        = rule.value["match_interface"]
      match_ip6_address                      = rule.value["match_ip6_address"]
      match_ip6_nexthop                      = rule.value["match_ip6_nexthop"]
      match_ip_address                       = rule.value["match_ip_address"]
      match_ip_nexthop                       = rule.value["match_ip_nexthop"]
      match_metric                           = rule.value["match_metric"]
      match_origin                           = rule.value["match_origin"]
      match_route_type                       = rule.value["match_route_type"]
      match_tag                              = rule.value["match_tag"]
      set_aggregator_as                      = rule.value["set_aggregator_as"]
      set_aggregator_ip                      = rule.value["set_aggregator_ip"]
      set_aspath_action                      = rule.value["set_aspath_action"]
      set_atomic_aggregate                   = rule.value["set_atomic_aggregate"]
      set_community_additive                 = rule.value["set_community_additive"]
      set_community_delete                   = rule.value["set_community_delete"]
      set_dampening_max_suppress             = rule.value["set_dampening_max_suppress"]
      set_dampening_reachability_half_life   = rule.value["set_dampening_reachability_half_life"]
      set_dampening_reuse                    = rule.value["set_dampening_reuse"]
      set_dampening_suppress                 = rule.value["set_dampening_suppress"]
      set_dampening_unreachability_half_life = rule.value["set_dampening_unreachability_half_life"]
      set_flags                              = rule.value["set_flags"]
      set_ip6_nexthop                        = rule.value["set_ip6_nexthop"]
      set_ip6_nexthop_local                  = rule.value["set_ip6_nexthop_local"]
      set_ip_nexthop                         = rule.value["set_ip_nexthop"]
      set_local_preference                   = rule.value["set_local_preference"]
      set_metric                             = rule.value["set_metric"]
      set_metric_type                        = rule.value["set_metric_type"]
      set_origin                             = rule.value["set_origin"]
      set_originator_id                      = rule.value["set_originator_id"]
      set_route_tag                          = rule.value["set_route_tag"]
      set_tag                                = rule.value["set_tag"]
      set_weight                             = rule.value["set_weight"]

      dynamic "set_aspath" {
        for_each = rule.value.set_aspath
        content {
          as = set_aspath.value["as"]
        }
      }

      dynamic "set_community" {
        for_each = rule.value.set_community
        content {
          community = set_community.value["community"]
        }
      }

      dynamic "set_extcommunity_rt" {
        for_each = rule.value.set_extcommunity_rt
        content {
          community = set_extcommunity_rt.value["community"]
        }
      }

      dynamic "set_extcommunity_soo" {
        for_each = rule.value.set_extcommunity_soo
        content {
          community = set_extcommunity_soo.value["community"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = fortios_router_routemap.this.comments
}

output "id" {
  description = "returns a string"
  value       = fortios_router_routemap.this.id
}

output "this" {
  value = fortios_router_routemap.this
}
```

[top](#index)