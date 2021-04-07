# fortios_routerbgp_neighbor

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
module "fortios_routerbgp_neighbor" {
  source = "./modules/fortios/d/fortios_routerbgp_neighbor"

  # ip - (required) is a type of string
  ip = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_routerbgp_neighbor" "this" {
  # ip - (required) is a type of string
  ip = var.ip
}
```

[top](#index)

### Outputs

```terraform
output "activate" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.activate
}

output "activate6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.activate6
}

output "additional_path" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.additional_path
}

output "additional_path6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.additional_path6
}

output "adv_additional_path" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.adv_additional_path
}

output "adv_additional_path6" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.adv_additional_path6
}

output "advertisement_interval" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.advertisement_interval
}

output "allowas_in" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.allowas_in
}

output "allowas_in6" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.allowas_in6
}

output "allowas_in_enable" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.allowas_in_enable
}

output "allowas_in_enable6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.allowas_in_enable6
}

output "as_override" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.as_override
}

output "as_override6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.as_override6
}

output "attribute_unchanged" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.attribute_unchanged
}

output "attribute_unchanged6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.attribute_unchanged6
}

output "bfd" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.bfd
}

output "capability_default_originate" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_default_originate
}

output "capability_default_originate6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_default_originate6
}

output "capability_dynamic" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_dynamic
}

output "capability_graceful_restart" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_graceful_restart
}

output "capability_graceful_restart6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_graceful_restart6
}

output "capability_orf" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_orf
}

output "capability_orf6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_orf6
}

output "capability_route_refresh" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.capability_route_refresh
}

output "conditional_advertise" {
  description = "returns a list of object"
  value       = data.fortios_routerbgp_neighbor.this.conditional_advertise
}

output "connect_timer" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.connect_timer
}

output "default_originate_routemap" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.default_originate_routemap
}

output "default_originate_routemap6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.default_originate_routemap6
}

output "description" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.description
}

output "distribute_list_in" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.distribute_list_in
}

output "distribute_list_in6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.distribute_list_in6
}

output "distribute_list_out" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.distribute_list_out
}

output "distribute_list_out6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.distribute_list_out6
}

output "dont_capability_negotiate" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.dont_capability_negotiate
}

output "ebgp_enforce_multihop" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.ebgp_enforce_multihop
}

output "ebgp_multihop_ttl" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.ebgp_multihop_ttl
}

output "filter_list_in" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.filter_list_in
}

output "filter_list_in6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.filter_list_in6
}

output "filter_list_out" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.filter_list_out
}

output "filter_list_out6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.filter_list_out6
}

output "holdtime_timer" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.holdtime_timer
}

output "id" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.interface
}

output "keep_alive_timer" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.keep_alive_timer
}

output "link_down_failover" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.link_down_failover
}

output "local_as" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.local_as
}

output "local_as_no_prepend" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.local_as_no_prepend
}

output "local_as_replace_as" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.local_as_replace_as
}

output "maximum_prefix" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.maximum_prefix
}

output "maximum_prefix6" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.maximum_prefix6
}

output "maximum_prefix_threshold" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.maximum_prefix_threshold
}

output "maximum_prefix_threshold6" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.maximum_prefix_threshold6
}

output "maximum_prefix_warning_only" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.maximum_prefix_warning_only
}

output "maximum_prefix_warning_only6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.maximum_prefix_warning_only6
}

output "next_hop_self" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.next_hop_self
}

output "next_hop_self6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.next_hop_self6
}

output "next_hop_self_rr" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.next_hop_self_rr
}

output "next_hop_self_rr6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.next_hop_self_rr6
}

output "override_capability" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.override_capability
}

output "passive" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.passive
}

output "password" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.password
  sensitive   = true
}

output "prefix_list_in" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.prefix_list_in
}

output "prefix_list_in6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.prefix_list_in6
}

output "prefix_list_out" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.prefix_list_out
}

output "prefix_list_out6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.prefix_list_out6
}

output "remote_as" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.remote_as
}

output "remove_private_as" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.remove_private_as
}

output "remove_private_as6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.remove_private_as6
}

output "restart_time" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.restart_time
}

output "retain_stale_time" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.retain_stale_time
}

output "route_map_in" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_map_in
}

output "route_map_in6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_map_in6
}

output "route_map_out" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_map_out
}

output "route_map_out6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_map_out6
}

output "route_map_out6_preferable" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_map_out6_preferable
}

output "route_map_out_preferable" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_map_out_preferable
}

output "route_reflector_client" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_reflector_client
}

output "route_reflector_client6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_reflector_client6
}

output "route_server_client" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_server_client
}

output "route_server_client6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.route_server_client6
}

output "send_community" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.send_community
}

output "send_community6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.send_community6
}

output "shutdown" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.shutdown
}

output "soft_reconfiguration" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.soft_reconfiguration
}

output "soft_reconfiguration6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.soft_reconfiguration6
}

output "stale_route" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.stale_route
}

output "strict_capability_match" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.strict_capability_match
}

output "unsuppress_map" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.unsuppress_map
}

output "unsuppress_map6" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.unsuppress_map6
}

output "update_source" {
  description = "returns a string"
  value       = data.fortios_routerbgp_neighbor.this.update_source
}

output "weight" {
  description = "returns a number"
  value       = data.fortios_routerbgp_neighbor.this.weight
}

output "this" {
  value = fortios_routerbgp_neighbor.this
}
```

[top](#index)