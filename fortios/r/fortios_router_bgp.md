# fortios_router_bgp

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_router_bgp" {
  source = "./modules/fortios/r/fortios_router_bgp"

  # additional_path - (optional) is a type of string
  additional_path = null
  # additional_path6 - (optional) is a type of string
  additional_path6 = null
  # additional_path_select - (optional) is a type of number
  additional_path_select = null
  # additional_path_select6 - (optional) is a type of number
  additional_path_select6 = null
  # always_compare_med - (optional) is a type of string
  always_compare_med = null
  # as - (required) is a type of number
  as = null
  # bestpath_as_path_ignore - (optional) is a type of string
  bestpath_as_path_ignore = null
  # bestpath_cmp_confed_aspath - (optional) is a type of string
  bestpath_cmp_confed_aspath = null
  # bestpath_cmp_routerid - (optional) is a type of string
  bestpath_cmp_routerid = null
  # bestpath_med_confed - (optional) is a type of string
  bestpath_med_confed = null
  # bestpath_med_missing_as_worst - (optional) is a type of string
  bestpath_med_missing_as_worst = null
  # client_to_client_reflection - (optional) is a type of string
  client_to_client_reflection = null
  # cluster_id - (optional) is a type of string
  cluster_id = null
  # confederation_identifier - (optional) is a type of number
  confederation_identifier = null
  # dampening - (optional) is a type of string
  dampening = null
  # dampening_max_suppress_time - (optional) is a type of number
  dampening_max_suppress_time = null
  # dampening_reachability_half_life - (optional) is a type of number
  dampening_reachability_half_life = null
  # dampening_reuse - (optional) is a type of number
  dampening_reuse = null
  # dampening_route_map - (optional) is a type of string
  dampening_route_map = null
  # dampening_suppress - (optional) is a type of number
  dampening_suppress = null
  # dampening_unreachability_half_life - (optional) is a type of number
  dampening_unreachability_half_life = null
  # default_local_preference - (optional) is a type of number
  default_local_preference = null
  # deterministic_med - (optional) is a type of string
  deterministic_med = null
  # distance_external - (optional) is a type of number
  distance_external = null
  # distance_internal - (optional) is a type of number
  distance_internal = null
  # distance_local - (optional) is a type of number
  distance_local = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ebgp_multipath - (optional) is a type of string
  ebgp_multipath = null
  # enforce_first_as - (optional) is a type of string
  enforce_first_as = null
  # fast_external_failover - (optional) is a type of string
  fast_external_failover = null
  # graceful_end_on_timer - (optional) is a type of string
  graceful_end_on_timer = null
  # graceful_restart - (optional) is a type of string
  graceful_restart = null
  # graceful_restart_time - (optional) is a type of number
  graceful_restart_time = null
  # graceful_stalepath_time - (optional) is a type of number
  graceful_stalepath_time = null
  # graceful_update_delay - (optional) is a type of number
  graceful_update_delay = null
  # holdtime_timer - (optional) is a type of number
  holdtime_timer = null
  # ibgp_multipath - (optional) is a type of string
  ibgp_multipath = null
  # ignore_optional_capability - (optional) is a type of string
  ignore_optional_capability = null
  # keepalive_timer - (optional) is a type of number
  keepalive_timer = null
  # log_neighbour_changes - (optional) is a type of string
  log_neighbour_changes = null
  # multipath_recursive_distance - (optional) is a type of string
  multipath_recursive_distance = null
  # network_import_check - (optional) is a type of string
  network_import_check = null
  # recursive_next_hop - (optional) is a type of string
  recursive_next_hop = null
  # router_id - (optional) is a type of string
  router_id = null
  # scan_time - (optional) is a type of number
  scan_time = null
  # synchronization - (optional) is a type of string
  synchronization = null

  admin_distance = [{
    distance         = null
    id               = null
    neighbour_prefix = null
    route_list       = null
  }]

  aggregate_address = [{
    as_set       = null
    id           = null
    prefix       = null
    summary_only = null
  }]

  aggregate_address6 = [{
    as_set       = null
    id           = null
    prefix6      = null
    summary_only = null
  }]

  confederation_peers = [{
    peer = null
  }]

  neighbor = [{
    activate                      = null
    activate6                     = null
    additional_path               = null
    additional_path6              = null
    adv_additional_path           = null
    adv_additional_path6          = null
    advertisement_interval        = null
    allowas_in                    = null
    allowas_in6                   = null
    allowas_in_enable             = null
    allowas_in_enable6            = null
    as_override                   = null
    as_override6                  = null
    attribute_unchanged           = null
    attribute_unchanged6          = null
    bfd                           = null
    capability_default_originate  = null
    capability_default_originate6 = null
    capability_dynamic            = null
    capability_graceful_restart   = null
    capability_graceful_restart6  = null
    capability_orf                = null
    capability_orf6               = null
    capability_route_refresh      = null
    conditional_advertise = [{
      advertise_routemap = null
      condition_routemap = null
      condition_type     = null
    }]
    connect_timer                = null
    default_originate_routemap   = null
    default_originate_routemap6  = null
    description                  = null
    distribute_list_in           = null
    distribute_list_in6          = null
    distribute_list_out          = null
    distribute_list_out6         = null
    dont_capability_negotiate    = null
    ebgp_enforce_multihop        = null
    ebgp_multihop_ttl            = null
    filter_list_in               = null
    filter_list_in6              = null
    filter_list_out              = null
    filter_list_out6             = null
    holdtime_timer               = null
    interface                    = null
    ip                           = null
    keep_alive_timer             = null
    link_down_failover           = null
    local_as                     = null
    local_as_no_prepend          = null
    local_as_replace_as          = null
    maximum_prefix               = null
    maximum_prefix6              = null
    maximum_prefix_threshold     = null
    maximum_prefix_threshold6    = null
    maximum_prefix_warning_only  = null
    maximum_prefix_warning_only6 = null
    next_hop_self                = null
    next_hop_self6               = null
    next_hop_self_rr             = null
    next_hop_self_rr6            = null
    override_capability          = null
    passive                      = null
    password                     = null
    prefix_list_in               = null
    prefix_list_in6              = null
    prefix_list_out              = null
    prefix_list_out6             = null
    remote_as                    = null
    remove_private_as            = null
    remove_private_as6           = null
    restart_time                 = null
    retain_stale_time            = null
    route_map_in                 = null
    route_map_in6                = null
    route_map_out                = null
    route_map_out6               = null
    route_map_out6_preferable    = null
    route_map_out_preferable     = null
    route_reflector_client       = null
    route_reflector_client6      = null
    route_server_client          = null
    route_server_client6         = null
    send_community               = null
    send_community6              = null
    shutdown                     = null
    soft_reconfiguration         = null
    soft_reconfiguration6        = null
    stale_route                  = null
    strict_capability_match      = null
    unsuppress_map               = null
    unsuppress_map6              = null
    update_source                = null
    weight                       = null
  }]

  neighbor_group = [{
    activate                      = null
    activate6                     = null
    additional_path               = null
    additional_path6              = null
    adv_additional_path           = null
    adv_additional_path6          = null
    advertisement_interval        = null
    allowas_in                    = null
    allowas_in6                   = null
    allowas_in_enable             = null
    allowas_in_enable6            = null
    as_override                   = null
    as_override6                  = null
    attribute_unchanged           = null
    attribute_unchanged6          = null
    bfd                           = null
    capability_default_originate  = null
    capability_default_originate6 = null
    capability_dynamic            = null
    capability_graceful_restart   = null
    capability_graceful_restart6  = null
    capability_orf                = null
    capability_orf6               = null
    capability_route_refresh      = null
    connect_timer                 = null
    default_originate_routemap    = null
    default_originate_routemap6   = null
    description                   = null
    distribute_list_in            = null
    distribute_list_in6           = null
    distribute_list_out           = null
    distribute_list_out6          = null
    dont_capability_negotiate     = null
    ebgp_enforce_multihop         = null
    ebgp_multihop_ttl             = null
    filter_list_in                = null
    filter_list_in6               = null
    filter_list_out               = null
    filter_list_out6              = null
    holdtime_timer                = null
    interface                     = null
    keep_alive_timer              = null
    link_down_failover            = null
    local_as                      = null
    local_as_no_prepend           = null
    local_as_replace_as           = null
    maximum_prefix                = null
    maximum_prefix6               = null
    maximum_prefix_threshold      = null
    maximum_prefix_threshold6     = null
    maximum_prefix_warning_only   = null
    maximum_prefix_warning_only6  = null
    name                          = null
    next_hop_self                 = null
    next_hop_self6                = null
    next_hop_self_rr              = null
    next_hop_self_rr6             = null
    override_capability           = null
    passive                       = null
    prefix_list_in                = null
    prefix_list_in6               = null
    prefix_list_out               = null
    prefix_list_out6              = null
    remote_as                     = null
    remove_private_as             = null
    remove_private_as6            = null
    restart_time                  = null
    retain_stale_time             = null
    route_map_in                  = null
    route_map_in6                 = null
    route_map_out                 = null
    route_map_out6                = null
    route_map_out6_preferable     = null
    route_map_out_preferable      = null
    route_reflector_client        = null
    route_reflector_client6       = null
    route_server_client           = null
    route_server_client6          = null
    send_community                = null
    send_community6               = null
    shutdown                      = null
    soft_reconfiguration          = null
    soft_reconfiguration6         = null
    stale_route                   = null
    strict_capability_match       = null
    unsuppress_map                = null
    unsuppress_map6               = null
    update_source                 = null
    weight                        = null
  }]

  neighbor_range = [{
    id               = null
    max_neighbor_num = null
    neighbor_group   = null
    prefix           = null
  }]

  neighbor_range6 = [{
    id               = null
    max_neighbor_num = null
    neighbor_group   = null
    prefix6          = null
  }]

  network = [{
    backdoor  = null
    id        = null
    prefix    = null
    route_map = null
  }]

  network6 = [{
    backdoor  = null
    id        = null
    prefix6   = null
    route_map = null
  }]

  redistribute = [{
    name      = null
    route_map = null
    status    = null
  }]

  redistribute6 = [{
    name      = null
    route_map = null
    status    = null
  }]

  vrf_leak = [{
    target = [{
      interface = null
      route_map = null
      vrf       = null
    }]
    vrf = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "additional_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "additional_path6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "additional_path_select" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "additional_path_select6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "always_compare_med" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "as" {
  description = "(required)"
  type        = number
}

variable "bestpath_as_path_ignore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bestpath_cmp_confed_aspath" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bestpath_cmp_routerid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bestpath_med_confed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bestpath_med_missing_as_worst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_to_client_reflection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "confederation_identifier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dampening" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dampening_max_suppress_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dampening_reachability_half_life" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dampening_reuse" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dampening_route_map" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dampening_suppress" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dampening_unreachability_half_life" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_local_preference" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "deterministic_med" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distance_external" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance_internal" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance_local" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebgp_multipath" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enforce_first_as" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fast_external_failover" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graceful_end_on_timer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graceful_restart" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graceful_restart_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "graceful_stalepath_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "graceful_update_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "holdtime_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ibgp_multipath" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_optional_capability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keepalive_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_neighbour_changes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multipath_recursive_distance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_import_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recursive_next_hop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "synchronization" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_distance" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      distance         = number
      id               = number
      neighbour_prefix = string
      route_list       = string
    }
  ))
  default = []
}

variable "aggregate_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      as_set       = string
      id           = number
      prefix       = string
      summary_only = string
    }
  ))
  default = []
}

variable "aggregate_address6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      as_set       = string
      id           = number
      prefix6      = string
      summary_only = string
    }
  ))
  default = []
}

variable "confederation_peers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      peer = string
    }
  ))
  default = []
}

variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      activate                      = string
      activate6                     = string
      additional_path               = string
      additional_path6              = string
      adv_additional_path           = number
      adv_additional_path6          = number
      advertisement_interval        = number
      allowas_in                    = number
      allowas_in6                   = number
      allowas_in_enable             = string
      allowas_in_enable6            = string
      as_override                   = string
      as_override6                  = string
      attribute_unchanged           = string
      attribute_unchanged6          = string
      bfd                           = string
      capability_default_originate  = string
      capability_default_originate6 = string
      capability_dynamic            = string
      capability_graceful_restart   = string
      capability_graceful_restart6  = string
      capability_orf                = string
      capability_orf6               = string
      capability_route_refresh      = string
      conditional_advertise = list(object(
        {
          advertise_routemap = string
          condition_routemap = string
          condition_type     = string
        }
      ))
      connect_timer                = number
      default_originate_routemap   = string
      default_originate_routemap6  = string
      description                  = string
      distribute_list_in           = string
      distribute_list_in6          = string
      distribute_list_out          = string
      distribute_list_out6         = string
      dont_capability_negotiate    = string
      ebgp_enforce_multihop        = string
      ebgp_multihop_ttl            = number
      filter_list_in               = string
      filter_list_in6              = string
      filter_list_out              = string
      filter_list_out6             = string
      holdtime_timer               = number
      interface                    = string
      ip                           = string
      keep_alive_timer             = number
      link_down_failover           = string
      local_as                     = number
      local_as_no_prepend          = string
      local_as_replace_as          = string
      maximum_prefix               = number
      maximum_prefix6              = number
      maximum_prefix_threshold     = number
      maximum_prefix_threshold6    = number
      maximum_prefix_warning_only  = string
      maximum_prefix_warning_only6 = string
      next_hop_self                = string
      next_hop_self6               = string
      next_hop_self_rr             = string
      next_hop_self_rr6            = string
      override_capability          = string
      passive                      = string
      password                     = string
      prefix_list_in               = string
      prefix_list_in6              = string
      prefix_list_out              = string
      prefix_list_out6             = string
      remote_as                    = number
      remove_private_as            = string
      remove_private_as6           = string
      restart_time                 = number
      retain_stale_time            = number
      route_map_in                 = string
      route_map_in6                = string
      route_map_out                = string
      route_map_out6               = string
      route_map_out6_preferable    = string
      route_map_out_preferable     = string
      route_reflector_client       = string
      route_reflector_client6      = string
      route_server_client          = string
      route_server_client6         = string
      send_community               = string
      send_community6              = string
      shutdown                     = string
      soft_reconfiguration         = string
      soft_reconfiguration6        = string
      stale_route                  = string
      strict_capability_match      = string
      unsuppress_map               = string
      unsuppress_map6              = string
      update_source                = string
      weight                       = number
    }
  ))
  default = []
}

variable "neighbor_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      activate                      = string
      activate6                     = string
      additional_path               = string
      additional_path6              = string
      adv_additional_path           = number
      adv_additional_path6          = number
      advertisement_interval        = number
      allowas_in                    = number
      allowas_in6                   = number
      allowas_in_enable             = string
      allowas_in_enable6            = string
      as_override                   = string
      as_override6                  = string
      attribute_unchanged           = string
      attribute_unchanged6          = string
      bfd                           = string
      capability_default_originate  = string
      capability_default_originate6 = string
      capability_dynamic            = string
      capability_graceful_restart   = string
      capability_graceful_restart6  = string
      capability_orf                = string
      capability_orf6               = string
      capability_route_refresh      = string
      connect_timer                 = number
      default_originate_routemap    = string
      default_originate_routemap6   = string
      description                   = string
      distribute_list_in            = string
      distribute_list_in6           = string
      distribute_list_out           = string
      distribute_list_out6          = string
      dont_capability_negotiate     = string
      ebgp_enforce_multihop         = string
      ebgp_multihop_ttl             = number
      filter_list_in                = string
      filter_list_in6               = string
      filter_list_out               = string
      filter_list_out6              = string
      holdtime_timer                = number
      interface                     = string
      keep_alive_timer              = number
      link_down_failover            = string
      local_as                      = number
      local_as_no_prepend           = string
      local_as_replace_as           = string
      maximum_prefix                = number
      maximum_prefix6               = number
      maximum_prefix_threshold      = number
      maximum_prefix_threshold6     = number
      maximum_prefix_warning_only   = string
      maximum_prefix_warning_only6  = string
      name                          = string
      next_hop_self                 = string
      next_hop_self6                = string
      next_hop_self_rr              = string
      next_hop_self_rr6             = string
      override_capability           = string
      passive                       = string
      prefix_list_in                = string
      prefix_list_in6               = string
      prefix_list_out               = string
      prefix_list_out6              = string
      remote_as                     = number
      remove_private_as             = string
      remove_private_as6            = string
      restart_time                  = number
      retain_stale_time             = number
      route_map_in                  = string
      route_map_in6                 = string
      route_map_out                 = string
      route_map_out6                = string
      route_map_out6_preferable     = string
      route_map_out_preferable      = string
      route_reflector_client        = string
      route_reflector_client6       = string
      route_server_client           = string
      route_server_client6          = string
      send_community                = string
      send_community6               = string
      shutdown                      = string
      soft_reconfiguration          = string
      soft_reconfiguration6         = string
      stale_route                   = string
      strict_capability_match       = string
      unsuppress_map                = string
      unsuppress_map6               = string
      update_source                 = string
      weight                        = number
    }
  ))
  default = []
}

variable "neighbor_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id               = number
      max_neighbor_num = number
      neighbor_group   = string
      prefix           = string
    }
  ))
  default = []
}

variable "neighbor_range6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id               = number
      max_neighbor_num = number
      neighbor_group   = string
      prefix6          = string
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      backdoor  = string
      id        = number
      prefix    = string
      route_map = string
    }
  ))
  default = []
}

variable "network6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      backdoor  = string
      id        = number
      prefix6   = string
      route_map = string
    }
  ))
  default = []
}

variable "redistribute" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name      = string
      route_map = string
      status    = string
    }
  ))
  default = []
}

variable "redistribute6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name      = string
      route_map = string
      status    = string
    }
  ))
  default = []
}

variable "vrf_leak" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      target = list(object(
        {
          interface = string
          route_map = string
          vrf       = string
        }
      ))
      vrf = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_bgp" "this" {
  additional_path                    = var.additional_path
  additional_path6                   = var.additional_path6
  additional_path_select             = var.additional_path_select
  additional_path_select6            = var.additional_path_select6
  always_compare_med                 = var.always_compare_med
  as                                 = var.as
  bestpath_as_path_ignore            = var.bestpath_as_path_ignore
  bestpath_cmp_confed_aspath         = var.bestpath_cmp_confed_aspath
  bestpath_cmp_routerid              = var.bestpath_cmp_routerid
  bestpath_med_confed                = var.bestpath_med_confed
  bestpath_med_missing_as_worst      = var.bestpath_med_missing_as_worst
  client_to_client_reflection        = var.client_to_client_reflection
  cluster_id                         = var.cluster_id
  confederation_identifier           = var.confederation_identifier
  dampening                          = var.dampening
  dampening_max_suppress_time        = var.dampening_max_suppress_time
  dampening_reachability_half_life   = var.dampening_reachability_half_life
  dampening_reuse                    = var.dampening_reuse
  dampening_route_map                = var.dampening_route_map
  dampening_suppress                 = var.dampening_suppress
  dampening_unreachability_half_life = var.dampening_unreachability_half_life
  default_local_preference           = var.default_local_preference
  deterministic_med                  = var.deterministic_med
  distance_external                  = var.distance_external
  distance_internal                  = var.distance_internal
  distance_local                     = var.distance_local
  dynamic_sort_subtable              = var.dynamic_sort_subtable
  ebgp_multipath                     = var.ebgp_multipath
  enforce_first_as                   = var.enforce_first_as
  fast_external_failover             = var.fast_external_failover
  graceful_end_on_timer              = var.graceful_end_on_timer
  graceful_restart                   = var.graceful_restart
  graceful_restart_time              = var.graceful_restart_time
  graceful_stalepath_time            = var.graceful_stalepath_time
  graceful_update_delay              = var.graceful_update_delay
  holdtime_timer                     = var.holdtime_timer
  ibgp_multipath                     = var.ibgp_multipath
  ignore_optional_capability         = var.ignore_optional_capability
  keepalive_timer                    = var.keepalive_timer
  log_neighbour_changes              = var.log_neighbour_changes
  multipath_recursive_distance       = var.multipath_recursive_distance
  network_import_check               = var.network_import_check
  recursive_next_hop                 = var.recursive_next_hop
  router_id                          = var.router_id
  scan_time                          = var.scan_time
  synchronization                    = var.synchronization

  dynamic "admin_distance" {
    for_each = var.admin_distance
    content {
      distance         = admin_distance.value["distance"]
      id               = admin_distance.value["id"]
      neighbour_prefix = admin_distance.value["neighbour_prefix"]
      route_list       = admin_distance.value["route_list"]
    }
  }

  dynamic "aggregate_address" {
    for_each = var.aggregate_address
    content {
      as_set       = aggregate_address.value["as_set"]
      id           = aggregate_address.value["id"]
      prefix       = aggregate_address.value["prefix"]
      summary_only = aggregate_address.value["summary_only"]
    }
  }

  dynamic "aggregate_address6" {
    for_each = var.aggregate_address6
    content {
      as_set       = aggregate_address6.value["as_set"]
      id           = aggregate_address6.value["id"]
      prefix6      = aggregate_address6.value["prefix6"]
      summary_only = aggregate_address6.value["summary_only"]
    }
  }

  dynamic "confederation_peers" {
    for_each = var.confederation_peers
    content {
      peer = confederation_peers.value["peer"]
    }
  }

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      activate                      = neighbor.value["activate"]
      activate6                     = neighbor.value["activate6"]
      additional_path               = neighbor.value["additional_path"]
      additional_path6              = neighbor.value["additional_path6"]
      adv_additional_path           = neighbor.value["adv_additional_path"]
      adv_additional_path6          = neighbor.value["adv_additional_path6"]
      advertisement_interval        = neighbor.value["advertisement_interval"]
      allowas_in                    = neighbor.value["allowas_in"]
      allowas_in6                   = neighbor.value["allowas_in6"]
      allowas_in_enable             = neighbor.value["allowas_in_enable"]
      allowas_in_enable6            = neighbor.value["allowas_in_enable6"]
      as_override                   = neighbor.value["as_override"]
      as_override6                  = neighbor.value["as_override6"]
      attribute_unchanged           = neighbor.value["attribute_unchanged"]
      attribute_unchanged6          = neighbor.value["attribute_unchanged6"]
      bfd                           = neighbor.value["bfd"]
      capability_default_originate  = neighbor.value["capability_default_originate"]
      capability_default_originate6 = neighbor.value["capability_default_originate6"]
      capability_dynamic            = neighbor.value["capability_dynamic"]
      capability_graceful_restart   = neighbor.value["capability_graceful_restart"]
      capability_graceful_restart6  = neighbor.value["capability_graceful_restart6"]
      capability_orf                = neighbor.value["capability_orf"]
      capability_orf6               = neighbor.value["capability_orf6"]
      capability_route_refresh      = neighbor.value["capability_route_refresh"]
      connect_timer                 = neighbor.value["connect_timer"]
      default_originate_routemap    = neighbor.value["default_originate_routemap"]
      default_originate_routemap6   = neighbor.value["default_originate_routemap6"]
      description                   = neighbor.value["description"]
      distribute_list_in            = neighbor.value["distribute_list_in"]
      distribute_list_in6           = neighbor.value["distribute_list_in6"]
      distribute_list_out           = neighbor.value["distribute_list_out"]
      distribute_list_out6          = neighbor.value["distribute_list_out6"]
      dont_capability_negotiate     = neighbor.value["dont_capability_negotiate"]
      ebgp_enforce_multihop         = neighbor.value["ebgp_enforce_multihop"]
      ebgp_multihop_ttl             = neighbor.value["ebgp_multihop_ttl"]
      filter_list_in                = neighbor.value["filter_list_in"]
      filter_list_in6               = neighbor.value["filter_list_in6"]
      filter_list_out               = neighbor.value["filter_list_out"]
      filter_list_out6              = neighbor.value["filter_list_out6"]
      holdtime_timer                = neighbor.value["holdtime_timer"]
      interface                     = neighbor.value["interface"]
      ip                            = neighbor.value["ip"]
      keep_alive_timer              = neighbor.value["keep_alive_timer"]
      link_down_failover            = neighbor.value["link_down_failover"]
      local_as                      = neighbor.value["local_as"]
      local_as_no_prepend           = neighbor.value["local_as_no_prepend"]
      local_as_replace_as           = neighbor.value["local_as_replace_as"]
      maximum_prefix                = neighbor.value["maximum_prefix"]
      maximum_prefix6               = neighbor.value["maximum_prefix6"]
      maximum_prefix_threshold      = neighbor.value["maximum_prefix_threshold"]
      maximum_prefix_threshold6     = neighbor.value["maximum_prefix_threshold6"]
      maximum_prefix_warning_only   = neighbor.value["maximum_prefix_warning_only"]
      maximum_prefix_warning_only6  = neighbor.value["maximum_prefix_warning_only6"]
      next_hop_self                 = neighbor.value["next_hop_self"]
      next_hop_self6                = neighbor.value["next_hop_self6"]
      next_hop_self_rr              = neighbor.value["next_hop_self_rr"]
      next_hop_self_rr6             = neighbor.value["next_hop_self_rr6"]
      override_capability           = neighbor.value["override_capability"]
      passive                       = neighbor.value["passive"]
      password                      = neighbor.value["password"]
      prefix_list_in                = neighbor.value["prefix_list_in"]
      prefix_list_in6               = neighbor.value["prefix_list_in6"]
      prefix_list_out               = neighbor.value["prefix_list_out"]
      prefix_list_out6              = neighbor.value["prefix_list_out6"]
      remote_as                     = neighbor.value["remote_as"]
      remove_private_as             = neighbor.value["remove_private_as"]
      remove_private_as6            = neighbor.value["remove_private_as6"]
      restart_time                  = neighbor.value["restart_time"]
      retain_stale_time             = neighbor.value["retain_stale_time"]
      route_map_in                  = neighbor.value["route_map_in"]
      route_map_in6                 = neighbor.value["route_map_in6"]
      route_map_out                 = neighbor.value["route_map_out"]
      route_map_out6                = neighbor.value["route_map_out6"]
      route_map_out6_preferable     = neighbor.value["route_map_out6_preferable"]
      route_map_out_preferable      = neighbor.value["route_map_out_preferable"]
      route_reflector_client        = neighbor.value["route_reflector_client"]
      route_reflector_client6       = neighbor.value["route_reflector_client6"]
      route_server_client           = neighbor.value["route_server_client"]
      route_server_client6          = neighbor.value["route_server_client6"]
      send_community                = neighbor.value["send_community"]
      send_community6               = neighbor.value["send_community6"]
      shutdown                      = neighbor.value["shutdown"]
      soft_reconfiguration          = neighbor.value["soft_reconfiguration"]
      soft_reconfiguration6         = neighbor.value["soft_reconfiguration6"]
      stale_route                   = neighbor.value["stale_route"]
      strict_capability_match       = neighbor.value["strict_capability_match"]
      unsuppress_map                = neighbor.value["unsuppress_map"]
      unsuppress_map6               = neighbor.value["unsuppress_map6"]
      update_source                 = neighbor.value["update_source"]
      weight                        = neighbor.value["weight"]

      dynamic "conditional_advertise" {
        for_each = neighbor.value.conditional_advertise
        content {
          advertise_routemap = conditional_advertise.value["advertise_routemap"]
          condition_routemap = conditional_advertise.value["condition_routemap"]
          condition_type     = conditional_advertise.value["condition_type"]
        }
      }

    }
  }

  dynamic "neighbor_group" {
    for_each = var.neighbor_group
    content {
      activate                      = neighbor_group.value["activate"]
      activate6                     = neighbor_group.value["activate6"]
      additional_path               = neighbor_group.value["additional_path"]
      additional_path6              = neighbor_group.value["additional_path6"]
      adv_additional_path           = neighbor_group.value["adv_additional_path"]
      adv_additional_path6          = neighbor_group.value["adv_additional_path6"]
      advertisement_interval        = neighbor_group.value["advertisement_interval"]
      allowas_in                    = neighbor_group.value["allowas_in"]
      allowas_in6                   = neighbor_group.value["allowas_in6"]
      allowas_in_enable             = neighbor_group.value["allowas_in_enable"]
      allowas_in_enable6            = neighbor_group.value["allowas_in_enable6"]
      as_override                   = neighbor_group.value["as_override"]
      as_override6                  = neighbor_group.value["as_override6"]
      attribute_unchanged           = neighbor_group.value["attribute_unchanged"]
      attribute_unchanged6          = neighbor_group.value["attribute_unchanged6"]
      bfd                           = neighbor_group.value["bfd"]
      capability_default_originate  = neighbor_group.value["capability_default_originate"]
      capability_default_originate6 = neighbor_group.value["capability_default_originate6"]
      capability_dynamic            = neighbor_group.value["capability_dynamic"]
      capability_graceful_restart   = neighbor_group.value["capability_graceful_restart"]
      capability_graceful_restart6  = neighbor_group.value["capability_graceful_restart6"]
      capability_orf                = neighbor_group.value["capability_orf"]
      capability_orf6               = neighbor_group.value["capability_orf6"]
      capability_route_refresh      = neighbor_group.value["capability_route_refresh"]
      connect_timer                 = neighbor_group.value["connect_timer"]
      default_originate_routemap    = neighbor_group.value["default_originate_routemap"]
      default_originate_routemap6   = neighbor_group.value["default_originate_routemap6"]
      description                   = neighbor_group.value["description"]
      distribute_list_in            = neighbor_group.value["distribute_list_in"]
      distribute_list_in6           = neighbor_group.value["distribute_list_in6"]
      distribute_list_out           = neighbor_group.value["distribute_list_out"]
      distribute_list_out6          = neighbor_group.value["distribute_list_out6"]
      dont_capability_negotiate     = neighbor_group.value["dont_capability_negotiate"]
      ebgp_enforce_multihop         = neighbor_group.value["ebgp_enforce_multihop"]
      ebgp_multihop_ttl             = neighbor_group.value["ebgp_multihop_ttl"]
      filter_list_in                = neighbor_group.value["filter_list_in"]
      filter_list_in6               = neighbor_group.value["filter_list_in6"]
      filter_list_out               = neighbor_group.value["filter_list_out"]
      filter_list_out6              = neighbor_group.value["filter_list_out6"]
      holdtime_timer                = neighbor_group.value["holdtime_timer"]
      interface                     = neighbor_group.value["interface"]
      keep_alive_timer              = neighbor_group.value["keep_alive_timer"]
      link_down_failover            = neighbor_group.value["link_down_failover"]
      local_as                      = neighbor_group.value["local_as"]
      local_as_no_prepend           = neighbor_group.value["local_as_no_prepend"]
      local_as_replace_as           = neighbor_group.value["local_as_replace_as"]
      maximum_prefix                = neighbor_group.value["maximum_prefix"]
      maximum_prefix6               = neighbor_group.value["maximum_prefix6"]
      maximum_prefix_threshold      = neighbor_group.value["maximum_prefix_threshold"]
      maximum_prefix_threshold6     = neighbor_group.value["maximum_prefix_threshold6"]
      maximum_prefix_warning_only   = neighbor_group.value["maximum_prefix_warning_only"]
      maximum_prefix_warning_only6  = neighbor_group.value["maximum_prefix_warning_only6"]
      name                          = neighbor_group.value["name"]
      next_hop_self                 = neighbor_group.value["next_hop_self"]
      next_hop_self6                = neighbor_group.value["next_hop_self6"]
      next_hop_self_rr              = neighbor_group.value["next_hop_self_rr"]
      next_hop_self_rr6             = neighbor_group.value["next_hop_self_rr6"]
      override_capability           = neighbor_group.value["override_capability"]
      passive                       = neighbor_group.value["passive"]
      prefix_list_in                = neighbor_group.value["prefix_list_in"]
      prefix_list_in6               = neighbor_group.value["prefix_list_in6"]
      prefix_list_out               = neighbor_group.value["prefix_list_out"]
      prefix_list_out6              = neighbor_group.value["prefix_list_out6"]
      remote_as                     = neighbor_group.value["remote_as"]
      remove_private_as             = neighbor_group.value["remove_private_as"]
      remove_private_as6            = neighbor_group.value["remove_private_as6"]
      restart_time                  = neighbor_group.value["restart_time"]
      retain_stale_time             = neighbor_group.value["retain_stale_time"]
      route_map_in                  = neighbor_group.value["route_map_in"]
      route_map_in6                 = neighbor_group.value["route_map_in6"]
      route_map_out                 = neighbor_group.value["route_map_out"]
      route_map_out6                = neighbor_group.value["route_map_out6"]
      route_map_out6_preferable     = neighbor_group.value["route_map_out6_preferable"]
      route_map_out_preferable      = neighbor_group.value["route_map_out_preferable"]
      route_reflector_client        = neighbor_group.value["route_reflector_client"]
      route_reflector_client6       = neighbor_group.value["route_reflector_client6"]
      route_server_client           = neighbor_group.value["route_server_client"]
      route_server_client6          = neighbor_group.value["route_server_client6"]
      send_community                = neighbor_group.value["send_community"]
      send_community6               = neighbor_group.value["send_community6"]
      shutdown                      = neighbor_group.value["shutdown"]
      soft_reconfiguration          = neighbor_group.value["soft_reconfiguration"]
      soft_reconfiguration6         = neighbor_group.value["soft_reconfiguration6"]
      stale_route                   = neighbor_group.value["stale_route"]
      strict_capability_match       = neighbor_group.value["strict_capability_match"]
      unsuppress_map                = neighbor_group.value["unsuppress_map"]
      unsuppress_map6               = neighbor_group.value["unsuppress_map6"]
      update_source                 = neighbor_group.value["update_source"]
      weight                        = neighbor_group.value["weight"]
    }
  }

  dynamic "neighbor_range" {
    for_each = var.neighbor_range
    content {
      id               = neighbor_range.value["id"]
      max_neighbor_num = neighbor_range.value["max_neighbor_num"]
      neighbor_group   = neighbor_range.value["neighbor_group"]
      prefix           = neighbor_range.value["prefix"]
    }
  }

  dynamic "neighbor_range6" {
    for_each = var.neighbor_range6
    content {
      id               = neighbor_range6.value["id"]
      max_neighbor_num = neighbor_range6.value["max_neighbor_num"]
      neighbor_group   = neighbor_range6.value["neighbor_group"]
      prefix6          = neighbor_range6.value["prefix6"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      backdoor  = network.value["backdoor"]
      id        = network.value["id"]
      prefix    = network.value["prefix"]
      route_map = network.value["route_map"]
    }
  }

  dynamic "network6" {
    for_each = var.network6
    content {
      backdoor  = network6.value["backdoor"]
      id        = network6.value["id"]
      prefix6   = network6.value["prefix6"]
      route_map = network6.value["route_map"]
    }
  }

  dynamic "redistribute" {
    for_each = var.redistribute
    content {
      name      = redistribute.value["name"]
      route_map = redistribute.value["route_map"]
      status    = redistribute.value["status"]
    }
  }

  dynamic "redistribute6" {
    for_each = var.redistribute6
    content {
      name      = redistribute6.value["name"]
      route_map = redistribute6.value["route_map"]
      status    = redistribute6.value["status"]
    }
  }

  dynamic "vrf_leak" {
    for_each = var.vrf_leak
    content {
      vrf = vrf_leak.value["vrf"]

      dynamic "target" {
        for_each = vrf_leak.value.target
        content {
          interface = target.value["interface"]
          route_map = target.value["route_map"]
          vrf       = target.value["vrf"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "additional_path" {
  description = "returns a string"
  value       = fortios_router_bgp.this.additional_path
}

output "additional_path6" {
  description = "returns a string"
  value       = fortios_router_bgp.this.additional_path6
}

output "additional_path_select" {
  description = "returns a number"
  value       = fortios_router_bgp.this.additional_path_select
}

output "additional_path_select6" {
  description = "returns a number"
  value       = fortios_router_bgp.this.additional_path_select6
}

output "always_compare_med" {
  description = "returns a string"
  value       = fortios_router_bgp.this.always_compare_med
}

output "bestpath_as_path_ignore" {
  description = "returns a string"
  value       = fortios_router_bgp.this.bestpath_as_path_ignore
}

output "bestpath_cmp_confed_aspath" {
  description = "returns a string"
  value       = fortios_router_bgp.this.bestpath_cmp_confed_aspath
}

output "bestpath_cmp_routerid" {
  description = "returns a string"
  value       = fortios_router_bgp.this.bestpath_cmp_routerid
}

output "bestpath_med_confed" {
  description = "returns a string"
  value       = fortios_router_bgp.this.bestpath_med_confed
}

output "bestpath_med_missing_as_worst" {
  description = "returns a string"
  value       = fortios_router_bgp.this.bestpath_med_missing_as_worst
}

output "client_to_client_reflection" {
  description = "returns a string"
  value       = fortios_router_bgp.this.client_to_client_reflection
}

output "cluster_id" {
  description = "returns a string"
  value       = fortios_router_bgp.this.cluster_id
}

output "confederation_identifier" {
  description = "returns a number"
  value       = fortios_router_bgp.this.confederation_identifier
}

output "dampening" {
  description = "returns a string"
  value       = fortios_router_bgp.this.dampening
}

output "dampening_max_suppress_time" {
  description = "returns a number"
  value       = fortios_router_bgp.this.dampening_max_suppress_time
}

output "dampening_reachability_half_life" {
  description = "returns a number"
  value       = fortios_router_bgp.this.dampening_reachability_half_life
}

output "dampening_reuse" {
  description = "returns a number"
  value       = fortios_router_bgp.this.dampening_reuse
}

output "dampening_route_map" {
  description = "returns a string"
  value       = fortios_router_bgp.this.dampening_route_map
}

output "dampening_suppress" {
  description = "returns a number"
  value       = fortios_router_bgp.this.dampening_suppress
}

output "dampening_unreachability_half_life" {
  description = "returns a number"
  value       = fortios_router_bgp.this.dampening_unreachability_half_life
}

output "default_local_preference" {
  description = "returns a number"
  value       = fortios_router_bgp.this.default_local_preference
}

output "deterministic_med" {
  description = "returns a string"
  value       = fortios_router_bgp.this.deterministic_med
}

output "distance_external" {
  description = "returns a number"
  value       = fortios_router_bgp.this.distance_external
}

output "distance_internal" {
  description = "returns a number"
  value       = fortios_router_bgp.this.distance_internal
}

output "distance_local" {
  description = "returns a number"
  value       = fortios_router_bgp.this.distance_local
}

output "ebgp_multipath" {
  description = "returns a string"
  value       = fortios_router_bgp.this.ebgp_multipath
}

output "enforce_first_as" {
  description = "returns a string"
  value       = fortios_router_bgp.this.enforce_first_as
}

output "fast_external_failover" {
  description = "returns a string"
  value       = fortios_router_bgp.this.fast_external_failover
}

output "graceful_end_on_timer" {
  description = "returns a string"
  value       = fortios_router_bgp.this.graceful_end_on_timer
}

output "graceful_restart" {
  description = "returns a string"
  value       = fortios_router_bgp.this.graceful_restart
}

output "graceful_restart_time" {
  description = "returns a number"
  value       = fortios_router_bgp.this.graceful_restart_time
}

output "graceful_stalepath_time" {
  description = "returns a number"
  value       = fortios_router_bgp.this.graceful_stalepath_time
}

output "graceful_update_delay" {
  description = "returns a number"
  value       = fortios_router_bgp.this.graceful_update_delay
}

output "holdtime_timer" {
  description = "returns a number"
  value       = fortios_router_bgp.this.holdtime_timer
}

output "ibgp_multipath" {
  description = "returns a string"
  value       = fortios_router_bgp.this.ibgp_multipath
}

output "id" {
  description = "returns a string"
  value       = fortios_router_bgp.this.id
}

output "ignore_optional_capability" {
  description = "returns a string"
  value       = fortios_router_bgp.this.ignore_optional_capability
}

output "keepalive_timer" {
  description = "returns a number"
  value       = fortios_router_bgp.this.keepalive_timer
}

output "log_neighbour_changes" {
  description = "returns a string"
  value       = fortios_router_bgp.this.log_neighbour_changes
}

output "multipath_recursive_distance" {
  description = "returns a string"
  value       = fortios_router_bgp.this.multipath_recursive_distance
}

output "network_import_check" {
  description = "returns a string"
  value       = fortios_router_bgp.this.network_import_check
}

output "recursive_next_hop" {
  description = "returns a string"
  value       = fortios_router_bgp.this.recursive_next_hop
}

output "router_id" {
  description = "returns a string"
  value       = fortios_router_bgp.this.router_id
}

output "scan_time" {
  description = "returns a number"
  value       = fortios_router_bgp.this.scan_time
}

output "synchronization" {
  description = "returns a string"
  value       = fortios_router_bgp.this.synchronization
}

output "this" {
  value = fortios_router_bgp.this
}
```

[top](#index)