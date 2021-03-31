# fortios_router_bgp

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_router_bgp"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_bgp" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "additional_path" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.additional_path
}

output "additional_path6" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.additional_path6
}

output "additional_path_select" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.additional_path_select
}

output "additional_path_select6" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.additional_path_select6
}

output "admin_distance" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.admin_distance
}

output "aggregate_address" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.aggregate_address
}

output "aggregate_address6" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.aggregate_address6
}

output "always_compare_med" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.always_compare_med
}

output "as" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.as
}

output "bestpath_as_path_ignore" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.bestpath_as_path_ignore
}

output "bestpath_cmp_confed_aspath" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.bestpath_cmp_confed_aspath
}

output "bestpath_cmp_routerid" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.bestpath_cmp_routerid
}

output "bestpath_med_confed" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.bestpath_med_confed
}

output "bestpath_med_missing_as_worst" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.bestpath_med_missing_as_worst
}

output "client_to_client_reflection" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.client_to_client_reflection
}

output "cluster_id" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.cluster_id
}

output "confederation_identifier" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.confederation_identifier
}

output "confederation_peers" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.confederation_peers
}

output "dampening" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.dampening
}

output "dampening_max_suppress_time" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.dampening_max_suppress_time
}

output "dampening_reachability_half_life" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.dampening_reachability_half_life
}

output "dampening_reuse" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.dampening_reuse
}

output "dampening_route_map" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.dampening_route_map
}

output "dampening_suppress" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.dampening_suppress
}

output "dampening_unreachability_half_life" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.dampening_unreachability_half_life
}

output "default_local_preference" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.default_local_preference
}

output "deterministic_med" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.deterministic_med
}

output "distance_external" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.distance_external
}

output "distance_internal" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.distance_internal
}

output "distance_local" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.distance_local
}

output "ebgp_multipath" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.ebgp_multipath
}

output "enforce_first_as" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.enforce_first_as
}

output "fast_external_failover" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.fast_external_failover
}

output "graceful_end_on_timer" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.graceful_end_on_timer
}

output "graceful_restart" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.graceful_restart
}

output "graceful_restart_time" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.graceful_restart_time
}

output "graceful_stalepath_time" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.graceful_stalepath_time
}

output "graceful_update_delay" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.graceful_update_delay
}

output "holdtime_timer" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.holdtime_timer
}

output "ibgp_multipath" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.ibgp_multipath
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.id
}

output "ignore_optional_capability" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.ignore_optional_capability
}

output "keepalive_timer" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.keepalive_timer
}

output "log_neighbour_changes" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.log_neighbour_changes
}

output "multipath_recursive_distance" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.multipath_recursive_distance
}

output "neighbor" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.neighbor
}

output "neighbor_group" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.neighbor_group
}

output "neighbor_range" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.neighbor_range
}

output "neighbor_range6" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.neighbor_range6
}

output "network" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.network
}

output "network6" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.network6
}

output "network_import_check" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.network_import_check
}

output "recursive_next_hop" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.recursive_next_hop
}

output "redistribute" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.redistribute
}

output "redistribute6" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.redistribute6
}

output "router_id" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.router_id
}

output "scan_time" {
  description = "returns a number"
  value       = data.fortios_router_bgp.this.scan_time
}

output "synchronization" {
  description = "returns a string"
  value       = data.fortios_router_bgp.this.synchronization
}

output "vrf_leak" {
  description = "returns a list of object"
  value       = data.fortios_router_bgp.this.vrf_leak
}

output "this" {
  value = fortios_router_bgp.this
}
```

[top](#index)