# fortios_routerbgp_neighbor

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
module "fortios_routerbgp_neighbor" {
  source = "./modules/fortios/r/fortios_routerbgp_neighbor"

  # activate - (optional) is a type of string
  activate = null
  # activate6 - (optional) is a type of string
  activate6 = null
  # additional_path - (optional) is a type of string
  additional_path = null
  # additional_path6 - (optional) is a type of string
  additional_path6 = null
  # adv_additional_path - (optional) is a type of number
  adv_additional_path = null
  # adv_additional_path6 - (optional) is a type of number
  adv_additional_path6 = null
  # advertisement_interval - (optional) is a type of number
  advertisement_interval = null
  # allowas_in - (optional) is a type of number
  allowas_in = null
  # allowas_in6 - (optional) is a type of number
  allowas_in6 = null
  # allowas_in_enable - (optional) is a type of string
  allowas_in_enable = null
  # allowas_in_enable6 - (optional) is a type of string
  allowas_in_enable6 = null
  # as_override - (optional) is a type of string
  as_override = null
  # as_override6 - (optional) is a type of string
  as_override6 = null
  # attribute_unchanged - (optional) is a type of string
  attribute_unchanged = null
  # attribute_unchanged6 - (optional) is a type of string
  attribute_unchanged6 = null
  # bfd - (optional) is a type of string
  bfd = null
  # capability_default_originate - (optional) is a type of string
  capability_default_originate = null
  # capability_default_originate6 - (optional) is a type of string
  capability_default_originate6 = null
  # capability_dynamic - (optional) is a type of string
  capability_dynamic = null
  # capability_graceful_restart - (optional) is a type of string
  capability_graceful_restart = null
  # capability_graceful_restart6 - (optional) is a type of string
  capability_graceful_restart6 = null
  # capability_orf - (optional) is a type of string
  capability_orf = null
  # capability_orf6 - (optional) is a type of string
  capability_orf6 = null
  # capability_route_refresh - (optional) is a type of string
  capability_route_refresh = null
  # connect_timer - (optional) is a type of number
  connect_timer = null
  # default_originate_routemap - (optional) is a type of string
  default_originate_routemap = null
  # default_originate_routemap6 - (optional) is a type of string
  default_originate_routemap6 = null
  # description - (optional) is a type of string
  description = null
  # distribute_list_in - (optional) is a type of string
  distribute_list_in = null
  # distribute_list_in6 - (optional) is a type of string
  distribute_list_in6 = null
  # distribute_list_out - (optional) is a type of string
  distribute_list_out = null
  # distribute_list_out6 - (optional) is a type of string
  distribute_list_out6 = null
  # dont_capability_negotiate - (optional) is a type of string
  dont_capability_negotiate = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ebgp_enforce_multihop - (optional) is a type of string
  ebgp_enforce_multihop = null
  # ebgp_multihop_ttl - (optional) is a type of number
  ebgp_multihop_ttl = null
  # filter_list_in - (optional) is a type of string
  filter_list_in = null
  # filter_list_in6 - (optional) is a type of string
  filter_list_in6 = null
  # filter_list_out - (optional) is a type of string
  filter_list_out = null
  # filter_list_out6 - (optional) is a type of string
  filter_list_out6 = null
  # holdtime_timer - (optional) is a type of number
  holdtime_timer = null
  # interface - (optional) is a type of string
  interface = null
  # ip - (required) is a type of string
  ip = null
  # keep_alive_timer - (optional) is a type of number
  keep_alive_timer = null
  # link_down_failover - (optional) is a type of string
  link_down_failover = null
  # local_as - (optional) is a type of number
  local_as = null
  # local_as_no_prepend - (optional) is a type of string
  local_as_no_prepend = null
  # local_as_replace_as - (optional) is a type of string
  local_as_replace_as = null
  # maximum_prefix - (optional) is a type of number
  maximum_prefix = null
  # maximum_prefix6 - (optional) is a type of number
  maximum_prefix6 = null
  # maximum_prefix_threshold - (optional) is a type of number
  maximum_prefix_threshold = null
  # maximum_prefix_threshold6 - (optional) is a type of number
  maximum_prefix_threshold6 = null
  # maximum_prefix_warning_only - (optional) is a type of string
  maximum_prefix_warning_only = null
  # maximum_prefix_warning_only6 - (optional) is a type of string
  maximum_prefix_warning_only6 = null
  # next_hop_self - (optional) is a type of string
  next_hop_self = null
  # next_hop_self6 - (optional) is a type of string
  next_hop_self6 = null
  # next_hop_self_rr - (optional) is a type of string
  next_hop_self_rr = null
  # next_hop_self_rr6 - (optional) is a type of string
  next_hop_self_rr6 = null
  # override_capability - (optional) is a type of string
  override_capability = null
  # passive - (optional) is a type of string
  passive = null
  # password - (optional) is a type of string
  password = null
  # prefix_list_in - (optional) is a type of string
  prefix_list_in = null
  # prefix_list_in6 - (optional) is a type of string
  prefix_list_in6 = null
  # prefix_list_out - (optional) is a type of string
  prefix_list_out = null
  # prefix_list_out6 - (optional) is a type of string
  prefix_list_out6 = null
  # remote_as - (optional) is a type of number
  remote_as = null
  # remove_private_as - (optional) is a type of string
  remove_private_as = null
  # remove_private_as6 - (optional) is a type of string
  remove_private_as6 = null
  # restart_time - (optional) is a type of number
  restart_time = null
  # retain_stale_time - (optional) is a type of number
  retain_stale_time = null
  # route_map_in - (optional) is a type of string
  route_map_in = null
  # route_map_in6 - (optional) is a type of string
  route_map_in6 = null
  # route_map_out - (optional) is a type of string
  route_map_out = null
  # route_map_out6 - (optional) is a type of string
  route_map_out6 = null
  # route_map_out6_preferable - (optional) is a type of string
  route_map_out6_preferable = null
  # route_map_out_preferable - (optional) is a type of string
  route_map_out_preferable = null
  # route_reflector_client - (optional) is a type of string
  route_reflector_client = null
  # route_reflector_client6 - (optional) is a type of string
  route_reflector_client6 = null
  # route_server_client - (optional) is a type of string
  route_server_client = null
  # route_server_client6 - (optional) is a type of string
  route_server_client6 = null
  # send_community - (optional) is a type of string
  send_community = null
  # send_community6 - (optional) is a type of string
  send_community6 = null
  # shutdown - (optional) is a type of string
  shutdown = null
  # soft_reconfiguration - (optional) is a type of string
  soft_reconfiguration = null
  # soft_reconfiguration6 - (optional) is a type of string
  soft_reconfiguration6 = null
  # stale_route - (optional) is a type of string
  stale_route = null
  # strict_capability_match - (optional) is a type of string
  strict_capability_match = null
  # unsuppress_map - (optional) is a type of string
  unsuppress_map = null
  # unsuppress_map6 - (optional) is a type of string
  unsuppress_map6 = null
  # update_source - (optional) is a type of string
  update_source = null
  # weight - (optional) is a type of number
  weight = null

  conditional_advertise = [{
    advertise_routemap = null
    condition_routemap = null
    condition_type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "activate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "activate6" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "adv_additional_path" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "adv_additional_path6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "advertisement_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allowas_in" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allowas_in6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allowas_in_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowas_in_enable6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "as_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "as_override6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attribute_unchanged" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attribute_unchanged6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bfd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_default_originate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_default_originate6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_dynamic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_graceful_restart" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_graceful_restart6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_orf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_orf6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capability_route_refresh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connect_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_originate_routemap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_originate_routemap6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distribute_list_in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distribute_list_in6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distribute_list_out" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distribute_list_out6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dont_capability_negotiate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebgp_enforce_multihop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ebgp_multihop_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "filter_list_in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_list_in6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_list_out" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_list_out6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "holdtime_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "keep_alive_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "link_down_failover" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_as" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_as_no_prepend" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_as_replace_as" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maximum_prefix" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_prefix6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_prefix_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_prefix_threshold6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_prefix_warning_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maximum_prefix_warning_only6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hop_self" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hop_self6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hop_self_rr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hop_self_rr6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_capability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix_list_in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix_list_in6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix_list_out" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix_list_out6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_as" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remove_private_as" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remove_private_as6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restart_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retain_stale_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "route_map_in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_map_in6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_map_out" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_map_out6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_map_out6_preferable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_map_out_preferable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_reflector_client" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_reflector_client6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_server_client" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_server_client6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "send_community" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "send_community6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shutdown" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "soft_reconfiguration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "soft_reconfiguration6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stale_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_capability_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unsuppress_map" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unsuppress_map6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conditional_advertise" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      advertise_routemap = string
      condition_routemap = string
      condition_type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_routerbgp_neighbor" "this" {
  # activate - (optional) is a type of string
  activate = var.activate
  # activate6 - (optional) is a type of string
  activate6 = var.activate6
  # additional_path - (optional) is a type of string
  additional_path = var.additional_path
  # additional_path6 - (optional) is a type of string
  additional_path6 = var.additional_path6
  # adv_additional_path - (optional) is a type of number
  adv_additional_path = var.adv_additional_path
  # adv_additional_path6 - (optional) is a type of number
  adv_additional_path6 = var.adv_additional_path6
  # advertisement_interval - (optional) is a type of number
  advertisement_interval = var.advertisement_interval
  # allowas_in - (optional) is a type of number
  allowas_in = var.allowas_in
  # allowas_in6 - (optional) is a type of number
  allowas_in6 = var.allowas_in6
  # allowas_in_enable - (optional) is a type of string
  allowas_in_enable = var.allowas_in_enable
  # allowas_in_enable6 - (optional) is a type of string
  allowas_in_enable6 = var.allowas_in_enable6
  # as_override - (optional) is a type of string
  as_override = var.as_override
  # as_override6 - (optional) is a type of string
  as_override6 = var.as_override6
  # attribute_unchanged - (optional) is a type of string
  attribute_unchanged = var.attribute_unchanged
  # attribute_unchanged6 - (optional) is a type of string
  attribute_unchanged6 = var.attribute_unchanged6
  # bfd - (optional) is a type of string
  bfd = var.bfd
  # capability_default_originate - (optional) is a type of string
  capability_default_originate = var.capability_default_originate
  # capability_default_originate6 - (optional) is a type of string
  capability_default_originate6 = var.capability_default_originate6
  # capability_dynamic - (optional) is a type of string
  capability_dynamic = var.capability_dynamic
  # capability_graceful_restart - (optional) is a type of string
  capability_graceful_restart = var.capability_graceful_restart
  # capability_graceful_restart6 - (optional) is a type of string
  capability_graceful_restart6 = var.capability_graceful_restart6
  # capability_orf - (optional) is a type of string
  capability_orf = var.capability_orf
  # capability_orf6 - (optional) is a type of string
  capability_orf6 = var.capability_orf6
  # capability_route_refresh - (optional) is a type of string
  capability_route_refresh = var.capability_route_refresh
  # connect_timer - (optional) is a type of number
  connect_timer = var.connect_timer
  # default_originate_routemap - (optional) is a type of string
  default_originate_routemap = var.default_originate_routemap
  # default_originate_routemap6 - (optional) is a type of string
  default_originate_routemap6 = var.default_originate_routemap6
  # description - (optional) is a type of string
  description = var.description
  # distribute_list_in - (optional) is a type of string
  distribute_list_in = var.distribute_list_in
  # distribute_list_in6 - (optional) is a type of string
  distribute_list_in6 = var.distribute_list_in6
  # distribute_list_out - (optional) is a type of string
  distribute_list_out = var.distribute_list_out
  # distribute_list_out6 - (optional) is a type of string
  distribute_list_out6 = var.distribute_list_out6
  # dont_capability_negotiate - (optional) is a type of string
  dont_capability_negotiate = var.dont_capability_negotiate
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # ebgp_enforce_multihop - (optional) is a type of string
  ebgp_enforce_multihop = var.ebgp_enforce_multihop
  # ebgp_multihop_ttl - (optional) is a type of number
  ebgp_multihop_ttl = var.ebgp_multihop_ttl
  # filter_list_in - (optional) is a type of string
  filter_list_in = var.filter_list_in
  # filter_list_in6 - (optional) is a type of string
  filter_list_in6 = var.filter_list_in6
  # filter_list_out - (optional) is a type of string
  filter_list_out = var.filter_list_out
  # filter_list_out6 - (optional) is a type of string
  filter_list_out6 = var.filter_list_out6
  # holdtime_timer - (optional) is a type of number
  holdtime_timer = var.holdtime_timer
  # interface - (optional) is a type of string
  interface = var.interface
  # ip - (required) is a type of string
  ip = var.ip
  # keep_alive_timer - (optional) is a type of number
  keep_alive_timer = var.keep_alive_timer
  # link_down_failover - (optional) is a type of string
  link_down_failover = var.link_down_failover
  # local_as - (optional) is a type of number
  local_as = var.local_as
  # local_as_no_prepend - (optional) is a type of string
  local_as_no_prepend = var.local_as_no_prepend
  # local_as_replace_as - (optional) is a type of string
  local_as_replace_as = var.local_as_replace_as
  # maximum_prefix - (optional) is a type of number
  maximum_prefix = var.maximum_prefix
  # maximum_prefix6 - (optional) is a type of number
  maximum_prefix6 = var.maximum_prefix6
  # maximum_prefix_threshold - (optional) is a type of number
  maximum_prefix_threshold = var.maximum_prefix_threshold
  # maximum_prefix_threshold6 - (optional) is a type of number
  maximum_prefix_threshold6 = var.maximum_prefix_threshold6
  # maximum_prefix_warning_only - (optional) is a type of string
  maximum_prefix_warning_only = var.maximum_prefix_warning_only
  # maximum_prefix_warning_only6 - (optional) is a type of string
  maximum_prefix_warning_only6 = var.maximum_prefix_warning_only6
  # next_hop_self - (optional) is a type of string
  next_hop_self = var.next_hop_self
  # next_hop_self6 - (optional) is a type of string
  next_hop_self6 = var.next_hop_self6
  # next_hop_self_rr - (optional) is a type of string
  next_hop_self_rr = var.next_hop_self_rr
  # next_hop_self_rr6 - (optional) is a type of string
  next_hop_self_rr6 = var.next_hop_self_rr6
  # override_capability - (optional) is a type of string
  override_capability = var.override_capability
  # passive - (optional) is a type of string
  passive = var.passive
  # password - (optional) is a type of string
  password = var.password
  # prefix_list_in - (optional) is a type of string
  prefix_list_in = var.prefix_list_in
  # prefix_list_in6 - (optional) is a type of string
  prefix_list_in6 = var.prefix_list_in6
  # prefix_list_out - (optional) is a type of string
  prefix_list_out = var.prefix_list_out
  # prefix_list_out6 - (optional) is a type of string
  prefix_list_out6 = var.prefix_list_out6
  # remote_as - (optional) is a type of number
  remote_as = var.remote_as
  # remove_private_as - (optional) is a type of string
  remove_private_as = var.remove_private_as
  # remove_private_as6 - (optional) is a type of string
  remove_private_as6 = var.remove_private_as6
  # restart_time - (optional) is a type of number
  restart_time = var.restart_time
  # retain_stale_time - (optional) is a type of number
  retain_stale_time = var.retain_stale_time
  # route_map_in - (optional) is a type of string
  route_map_in = var.route_map_in
  # route_map_in6 - (optional) is a type of string
  route_map_in6 = var.route_map_in6
  # route_map_out - (optional) is a type of string
  route_map_out = var.route_map_out
  # route_map_out6 - (optional) is a type of string
  route_map_out6 = var.route_map_out6
  # route_map_out6_preferable - (optional) is a type of string
  route_map_out6_preferable = var.route_map_out6_preferable
  # route_map_out_preferable - (optional) is a type of string
  route_map_out_preferable = var.route_map_out_preferable
  # route_reflector_client - (optional) is a type of string
  route_reflector_client = var.route_reflector_client
  # route_reflector_client6 - (optional) is a type of string
  route_reflector_client6 = var.route_reflector_client6
  # route_server_client - (optional) is a type of string
  route_server_client = var.route_server_client
  # route_server_client6 - (optional) is a type of string
  route_server_client6 = var.route_server_client6
  # send_community - (optional) is a type of string
  send_community = var.send_community
  # send_community6 - (optional) is a type of string
  send_community6 = var.send_community6
  # shutdown - (optional) is a type of string
  shutdown = var.shutdown
  # soft_reconfiguration - (optional) is a type of string
  soft_reconfiguration = var.soft_reconfiguration
  # soft_reconfiguration6 - (optional) is a type of string
  soft_reconfiguration6 = var.soft_reconfiguration6
  # stale_route - (optional) is a type of string
  stale_route = var.stale_route
  # strict_capability_match - (optional) is a type of string
  strict_capability_match = var.strict_capability_match
  # unsuppress_map - (optional) is a type of string
  unsuppress_map = var.unsuppress_map
  # unsuppress_map6 - (optional) is a type of string
  unsuppress_map6 = var.unsuppress_map6
  # update_source - (optional) is a type of string
  update_source = var.update_source
  # weight - (optional) is a type of number
  weight = var.weight

  dynamic "conditional_advertise" {
    for_each = var.conditional_advertise
    content {
      # advertise_routemap - (optional) is a type of string
      advertise_routemap = conditional_advertise.value["advertise_routemap"]
      # condition_routemap - (optional) is a type of string
      condition_routemap = conditional_advertise.value["condition_routemap"]
      # condition_type - (optional) is a type of string
      condition_type = conditional_advertise.value["condition_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "activate" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.activate
}

output "activate6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.activate6
}

output "additional_path" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.additional_path
}

output "additional_path6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.additional_path6
}

output "adv_additional_path" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.adv_additional_path
}

output "adv_additional_path6" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.adv_additional_path6
}

output "advertisement_interval" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.advertisement_interval
}

output "allowas_in" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.allowas_in
}

output "allowas_in6" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.allowas_in6
}

output "allowas_in_enable" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.allowas_in_enable
}

output "allowas_in_enable6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.allowas_in_enable6
}

output "as_override" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.as_override
}

output "as_override6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.as_override6
}

output "attribute_unchanged" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.attribute_unchanged
}

output "attribute_unchanged6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.attribute_unchanged6
}

output "bfd" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.bfd
}

output "capability_default_originate" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_default_originate
}

output "capability_default_originate6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_default_originate6
}

output "capability_dynamic" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_dynamic
}

output "capability_graceful_restart" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_graceful_restart
}

output "capability_graceful_restart6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_graceful_restart6
}

output "capability_orf" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_orf
}

output "capability_orf6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_orf6
}

output "capability_route_refresh" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.capability_route_refresh
}

output "connect_timer" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.connect_timer
}

output "default_originate_routemap" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.default_originate_routemap
}

output "default_originate_routemap6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.default_originate_routemap6
}

output "description" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.description
}

output "distribute_list_in" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.distribute_list_in
}

output "distribute_list_in6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.distribute_list_in6
}

output "distribute_list_out" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.distribute_list_out
}

output "distribute_list_out6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.distribute_list_out6
}

output "dont_capability_negotiate" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.dont_capability_negotiate
}

output "ebgp_enforce_multihop" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.ebgp_enforce_multihop
}

output "ebgp_multihop_ttl" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.ebgp_multihop_ttl
}

output "filter_list_in" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.filter_list_in
}

output "filter_list_in6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.filter_list_in6
}

output "filter_list_out" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.filter_list_out
}

output "filter_list_out6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.filter_list_out6
}

output "holdtime_timer" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.holdtime_timer
}

output "id" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.interface
}

output "keep_alive_timer" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.keep_alive_timer
}

output "link_down_failover" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.link_down_failover
}

output "local_as" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.local_as
}

output "local_as_no_prepend" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.local_as_no_prepend
}

output "local_as_replace_as" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.local_as_replace_as
}

output "maximum_prefix" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.maximum_prefix
}

output "maximum_prefix6" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.maximum_prefix6
}

output "maximum_prefix_threshold" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.maximum_prefix_threshold
}

output "maximum_prefix_threshold6" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.maximum_prefix_threshold6
}

output "maximum_prefix_warning_only" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.maximum_prefix_warning_only
}

output "maximum_prefix_warning_only6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.maximum_prefix_warning_only6
}

output "next_hop_self" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.next_hop_self
}

output "next_hop_self6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.next_hop_self6
}

output "next_hop_self_rr" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.next_hop_self_rr
}

output "next_hop_self_rr6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.next_hop_self_rr6
}

output "override_capability" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.override_capability
}

output "passive" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.passive
}

output "prefix_list_in" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.prefix_list_in
}

output "prefix_list_in6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.prefix_list_in6
}

output "prefix_list_out" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.prefix_list_out
}

output "prefix_list_out6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.prefix_list_out6
}

output "remote_as" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.remote_as
}

output "remove_private_as" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.remove_private_as
}

output "remove_private_as6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.remove_private_as6
}

output "restart_time" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.restart_time
}

output "retain_stale_time" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.retain_stale_time
}

output "route_map_in" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_map_in
}

output "route_map_in6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_map_in6
}

output "route_map_out" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_map_out
}

output "route_map_out6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_map_out6
}

output "route_map_out6_preferable" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_map_out6_preferable
}

output "route_map_out_preferable" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_map_out_preferable
}

output "route_reflector_client" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_reflector_client
}

output "route_reflector_client6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_reflector_client6
}

output "route_server_client" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_server_client
}

output "route_server_client6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.route_server_client6
}

output "send_community" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.send_community
}

output "send_community6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.send_community6
}

output "shutdown" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.shutdown
}

output "soft_reconfiguration" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.soft_reconfiguration
}

output "soft_reconfiguration6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.soft_reconfiguration6
}

output "stale_route" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.stale_route
}

output "strict_capability_match" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.strict_capability_match
}

output "unsuppress_map" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.unsuppress_map
}

output "unsuppress_map6" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.unsuppress_map6
}

output "update_source" {
  description = "returns a string"
  value       = fortios_routerbgp_neighbor.this.update_source
}

output "weight" {
  description = "returns a number"
  value       = fortios_routerbgp_neighbor.this.weight
}

output "this" {
  value = fortios_routerbgp_neighbor.this
}
```

[top](#index)