# fortios_router_multicast

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
module "fortios_router_multicast" {
  source = "./modules/fortios/r/fortios_router_multicast"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # multicast_routing - (optional) is a type of string
  multicast_routing = null
  # route_limit - (optional) is a type of number
  route_limit = null
  # route_threshold - (optional) is a type of number
  route_threshold = null

  interface = [{
    bfd                 = null
    cisco_exclude_genid = null
    dr_priority         = null
    hello_holdtime      = null
    hello_interval      = null
    igmp = [{
      access_group               = null
      immediate_leave_group      = null
      last_member_query_count    = null
      last_member_query_interval = null
      query_interval             = null
      query_max_response_time    = null
      query_timeout              = null
      router_alert_check         = null
      version                    = null
    }]
    join_group = [{
      address = null
    }]
    multicast_flow           = null
    name                     = null
    neighbour_filter         = null
    passive                  = null
    pim_mode                 = null
    propagation_delay        = null
    rp_candidate             = null
    rp_candidate_group       = null
    rp_candidate_interval    = null
    rp_candidate_priority    = null
    rpf_nbr_fail_back        = null
    rpf_nbr_fail_back_filter = null
    state_refresh_interval   = null
    static_group             = null
    ttl_threshold            = null
  }]

  pim_sm_global = [{
    accept_register_list          = null
    accept_source_list            = null
    bsr_allow_quick_refresh       = null
    bsr_candidate                 = null
    bsr_hash                      = null
    bsr_interface                 = null
    bsr_priority                  = null
    cisco_crp_prefix              = null
    cisco_ignore_rp_set_priority  = null
    cisco_register_checksum       = null
    cisco_register_checksum_group = null
    join_prune_holdtime           = null
    message_interval              = null
    null_register_retries         = null
    register_rate_limit           = null
    register_rp_reachability      = null
    register_source               = null
    register_source_interface     = null
    register_source_ip            = null
    register_supression           = null
    rp_address = [{
      group      = null
      id         = null
      ip_address = null
    }]
    rp_register_keepalive = null
    spt_threshold         = null
    spt_threshold_group   = null
    ssm                   = null
    ssm_range             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "route_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bfd                 = string
      cisco_exclude_genid = string
      dr_priority         = number
      hello_holdtime      = number
      hello_interval      = number
      igmp = list(object(
        {
          access_group               = string
          immediate_leave_group      = string
          last_member_query_count    = number
          last_member_query_interval = number
          query_interval             = number
          query_max_response_time    = number
          query_timeout              = number
          router_alert_check         = string
          version                    = string
        }
      ))
      join_group = list(object(
        {
          address = string
        }
      ))
      multicast_flow           = string
      name                     = string
      neighbour_filter         = string
      passive                  = string
      pim_mode                 = string
      propagation_delay        = number
      rp_candidate             = string
      rp_candidate_group       = string
      rp_candidate_interval    = number
      rp_candidate_priority    = number
      rpf_nbr_fail_back        = string
      rpf_nbr_fail_back_filter = string
      state_refresh_interval   = number
      static_group             = string
      ttl_threshold            = number
    }
  ))
  default = []
}

variable "pim_sm_global" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      accept_register_list          = string
      accept_source_list            = string
      bsr_allow_quick_refresh       = string
      bsr_candidate                 = string
      bsr_hash                      = number
      bsr_interface                 = string
      bsr_priority                  = number
      cisco_crp_prefix              = string
      cisco_ignore_rp_set_priority  = string
      cisco_register_checksum       = string
      cisco_register_checksum_group = string
      join_prune_holdtime           = number
      message_interval              = number
      null_register_retries         = number
      register_rate_limit           = number
      register_rp_reachability      = string
      register_source               = string
      register_source_interface     = string
      register_source_ip            = string
      register_supression           = number
      rp_address = list(object(
        {
          group      = string
          id         = number
          ip_address = string
        }
      ))
      rp_register_keepalive = number
      spt_threshold         = string
      spt_threshold_group   = string
      ssm                   = string
      ssm_range             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_multicast" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  multicast_routing     = var.multicast_routing
  route_limit           = var.route_limit
  route_threshold       = var.route_threshold

  dynamic "interface" {
    for_each = var.interface
    content {
      bfd                      = interface.value["bfd"]
      cisco_exclude_genid      = interface.value["cisco_exclude_genid"]
      dr_priority              = interface.value["dr_priority"]
      hello_holdtime           = interface.value["hello_holdtime"]
      hello_interval           = interface.value["hello_interval"]
      multicast_flow           = interface.value["multicast_flow"]
      name                     = interface.value["name"]
      neighbour_filter         = interface.value["neighbour_filter"]
      passive                  = interface.value["passive"]
      pim_mode                 = interface.value["pim_mode"]
      propagation_delay        = interface.value["propagation_delay"]
      rp_candidate             = interface.value["rp_candidate"]
      rp_candidate_group       = interface.value["rp_candidate_group"]
      rp_candidate_interval    = interface.value["rp_candidate_interval"]
      rp_candidate_priority    = interface.value["rp_candidate_priority"]
      rpf_nbr_fail_back        = interface.value["rpf_nbr_fail_back"]
      rpf_nbr_fail_back_filter = interface.value["rpf_nbr_fail_back_filter"]
      state_refresh_interval   = interface.value["state_refresh_interval"]
      static_group             = interface.value["static_group"]
      ttl_threshold            = interface.value["ttl_threshold"]

      dynamic "igmp" {
        for_each = interface.value.igmp
        content {
          access_group               = igmp.value["access_group"]
          immediate_leave_group      = igmp.value["immediate_leave_group"]
          last_member_query_count    = igmp.value["last_member_query_count"]
          last_member_query_interval = igmp.value["last_member_query_interval"]
          query_interval             = igmp.value["query_interval"]
          query_max_response_time    = igmp.value["query_max_response_time"]
          query_timeout              = igmp.value["query_timeout"]
          router_alert_check         = igmp.value["router_alert_check"]
          version                    = igmp.value["version"]
        }
      }

      dynamic "join_group" {
        for_each = interface.value.join_group
        content {
          address = join_group.value["address"]
        }
      }

    }
  }

  dynamic "pim_sm_global" {
    for_each = var.pim_sm_global
    content {
      accept_register_list          = pim_sm_global.value["accept_register_list"]
      accept_source_list            = pim_sm_global.value["accept_source_list"]
      bsr_allow_quick_refresh       = pim_sm_global.value["bsr_allow_quick_refresh"]
      bsr_candidate                 = pim_sm_global.value["bsr_candidate"]
      bsr_hash                      = pim_sm_global.value["bsr_hash"]
      bsr_interface                 = pim_sm_global.value["bsr_interface"]
      bsr_priority                  = pim_sm_global.value["bsr_priority"]
      cisco_crp_prefix              = pim_sm_global.value["cisco_crp_prefix"]
      cisco_ignore_rp_set_priority  = pim_sm_global.value["cisco_ignore_rp_set_priority"]
      cisco_register_checksum       = pim_sm_global.value["cisco_register_checksum"]
      cisco_register_checksum_group = pim_sm_global.value["cisco_register_checksum_group"]
      join_prune_holdtime           = pim_sm_global.value["join_prune_holdtime"]
      message_interval              = pim_sm_global.value["message_interval"]
      null_register_retries         = pim_sm_global.value["null_register_retries"]
      register_rate_limit           = pim_sm_global.value["register_rate_limit"]
      register_rp_reachability      = pim_sm_global.value["register_rp_reachability"]
      register_source               = pim_sm_global.value["register_source"]
      register_source_interface     = pim_sm_global.value["register_source_interface"]
      register_source_ip            = pim_sm_global.value["register_source_ip"]
      register_supression           = pim_sm_global.value["register_supression"]
      rp_register_keepalive         = pim_sm_global.value["rp_register_keepalive"]
      spt_threshold                 = pim_sm_global.value["spt_threshold"]
      spt_threshold_group           = pim_sm_global.value["spt_threshold_group"]
      ssm                           = pim_sm_global.value["ssm"]
      ssm_range                     = pim_sm_global.value["ssm_range"]

      dynamic "rp_address" {
        for_each = pim_sm_global.value.rp_address
        content {
          group      = rp_address.value["group"]
          id         = rp_address.value["id"]
          ip_address = rp_address.value["ip_address"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_multicast.this.id
}

output "multicast_routing" {
  description = "returns a string"
  value       = fortios_router_multicast.this.multicast_routing
}

output "route_limit" {
  description = "returns a number"
  value       = fortios_router_multicast.this.route_limit
}

output "route_threshold" {
  description = "returns a number"
  value       = fortios_router_multicast.this.route_threshold
}

output "this" {
  value = fortios_router_multicast.this
}
```

[top](#index)