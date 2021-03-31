# fortios_router_ospf

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
module "fortios_router_ospf" {
  source = "./modules/fortios/r/fortios_router_ospf"

  # abr_type - (optional) is a type of string
  abr_type = null
  # auto_cost_ref_bandwidth - (optional) is a type of number
  auto_cost_ref_bandwidth = null
  # bfd - (optional) is a type of string
  bfd = null
  # database_overflow - (optional) is a type of string
  database_overflow = null
  # database_overflow_max_lsas - (optional) is a type of number
  database_overflow_max_lsas = null
  # database_overflow_time_to_recover - (optional) is a type of number
  database_overflow_time_to_recover = null
  # default_information_metric - (optional) is a type of number
  default_information_metric = null
  # default_information_metric_type - (optional) is a type of string
  default_information_metric_type = null
  # default_information_originate - (optional) is a type of string
  default_information_originate = null
  # default_information_route_map - (optional) is a type of string
  default_information_route_map = null
  # default_metric - (optional) is a type of number
  default_metric = null
  # distance - (optional) is a type of number
  distance = null
  # distance_external - (optional) is a type of number
  distance_external = null
  # distance_inter_area - (optional) is a type of number
  distance_inter_area = null
  # distance_intra_area - (optional) is a type of number
  distance_intra_area = null
  # distribute_list_in - (optional) is a type of string
  distribute_list_in = null
  # distribute_route_map_in - (optional) is a type of string
  distribute_route_map_in = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # log_neighbour_changes - (optional) is a type of string
  log_neighbour_changes = null
  # restart_mode - (optional) is a type of string
  restart_mode = null
  # restart_period - (optional) is a type of number
  restart_period = null
  # rfc1583_compatible - (optional) is a type of string
  rfc1583_compatible = null
  # router_id - (required) is a type of string
  router_id = null
  # spf_timers - (optional) is a type of string
  spf_timers = null

  area = [{
    authentication = null
    default_cost   = null
    filter_list = [{
      direction = null
      id        = null
      list      = null
    }]
    id                                             = null
    nssa_default_information_originate             = null
    nssa_default_information_originate_metric      = null
    nssa_default_information_originate_metric_type = null
    nssa_redistribution                            = null
    nssa_translator_role                           = null
    range = [{
      advertise         = null
      id                = null
      prefix            = null
      substitute        = null
      substitute_status = null
    }]
    shortcut  = null
    stub_type = null
    type      = null
    virtual_link = [{
      authentication     = null
      authentication_key = null
      dead_interval      = null
      hello_interval     = null
      md5_key            = null
      md5_keychain       = null
      md5_keys = [{
        id         = null
        key_string = null
      }]
      name                = null
      peer                = null
      retransmit_interval = null
      transmit_delay      = null
    }]
  }]

  distribute_list = [{
    access_list = null
    id          = null
    protocol    = null
  }]

  neighbor = [{
    cost          = null
    id            = null
    ip            = null
    poll_interval = null
    priority      = null
  }]

  network = [{
    area   = null
    id     = null
    prefix = null
  }]

  ospf_interface = [{
    authentication      = null
    authentication_key  = null
    bfd                 = null
    cost                = null
    database_filter_out = null
    dead_interval       = null
    hello_interval      = null
    hello_multiplier    = null
    interface           = null
    ip                  = null
    md5_key             = null
    md5_keychain        = null
    md5_keys = [{
      id         = null
      key_string = null
    }]
    mtu                 = null
    mtu_ignore          = null
    name                = null
    network_type        = null
    prefix_length       = null
    priority            = null
    resync_timeout      = null
    retransmit_interval = null
    status              = null
    transmit_delay      = null
  }]

  passive_interface = [{
    name = null
  }]

  redistribute = [{
    metric      = null
    metric_type = null
    name        = null
    routemap    = null
    status      = null
    tag         = null
  }]

  summary_address = [{
    advertise = null
    id        = null
    prefix    = null
    tag       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "abr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_cost_ref_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bfd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_overflow" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_overflow_max_lsas" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "database_overflow_time_to_recover" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_information_metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_information_metric_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_information_originate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_information_route_map" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance_external" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance_inter_area" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance_intra_area" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distribute_list_in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distribute_route_map_in" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_neighbour_changes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restart_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restart_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rfc1583_compatible" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router_id" {
  description = "(required)"
  type        = string
}

variable "spf_timers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "area" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      authentication = string
      default_cost   = number
      filter_list = list(object(
        {
          direction = string
          id        = number
          list      = string
        }
      ))
      id                                             = string
      nssa_default_information_originate             = string
      nssa_default_information_originate_metric      = number
      nssa_default_information_originate_metric_type = string
      nssa_redistribution                            = string
      nssa_translator_role                           = string
      range = list(object(
        {
          advertise         = string
          id                = number
          prefix            = string
          substitute        = string
          substitute_status = string
        }
      ))
      shortcut  = string
      stub_type = string
      type      = string
      virtual_link = list(object(
        {
          authentication     = string
          authentication_key = string
          dead_interval      = number
          hello_interval     = number
          md5_key            = string
          md5_keychain       = string
          md5_keys = list(object(
            {
              id         = number
              key_string = string
            }
          ))
          name                = string
          peer                = string
          retransmit_interval = number
          transmit_delay      = number
        }
      ))
    }
  ))
  default = []
}

variable "distribute_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_list = string
      id          = number
      protocol    = string
    }
  ))
  default = []
}

variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cost          = number
      id            = number
      ip            = string
      poll_interval = number
      priority      = number
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      area   = string
      id     = number
      prefix = string
    }
  ))
  default = []
}

variable "ospf_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      authentication      = string
      authentication_key  = string
      bfd                 = string
      cost                = number
      database_filter_out = string
      dead_interval       = number
      hello_interval      = number
      hello_multiplier    = number
      interface           = string
      ip                  = string
      md5_key             = string
      md5_keychain        = string
      md5_keys = list(object(
        {
          id         = number
          key_string = string
        }
      ))
      mtu                 = number
      mtu_ignore          = string
      name                = string
      network_type        = string
      prefix_length       = number
      priority            = number
      resync_timeout      = number
      retransmit_interval = number
      status              = string
      transmit_delay      = number
    }
  ))
  default = []
}

variable "passive_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "redistribute" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      metric      = number
      metric_type = string
      name        = string
      routemap    = string
      status      = string
      tag         = number
    }
  ))
  default = []
}

variable "summary_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      advertise = string
      id        = number
      prefix    = string
      tag       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_ospf" "this" {
  abr_type                          = var.abr_type
  auto_cost_ref_bandwidth           = var.auto_cost_ref_bandwidth
  bfd                               = var.bfd
  database_overflow                 = var.database_overflow
  database_overflow_max_lsas        = var.database_overflow_max_lsas
  database_overflow_time_to_recover = var.database_overflow_time_to_recover
  default_information_metric        = var.default_information_metric
  default_information_metric_type   = var.default_information_metric_type
  default_information_originate     = var.default_information_originate
  default_information_route_map     = var.default_information_route_map
  default_metric                    = var.default_metric
  distance                          = var.distance
  distance_external                 = var.distance_external
  distance_inter_area               = var.distance_inter_area
  distance_intra_area               = var.distance_intra_area
  distribute_list_in                = var.distribute_list_in
  distribute_route_map_in           = var.distribute_route_map_in
  dynamic_sort_subtable             = var.dynamic_sort_subtable
  log_neighbour_changes             = var.log_neighbour_changes
  restart_mode                      = var.restart_mode
  restart_period                    = var.restart_period
  rfc1583_compatible                = var.rfc1583_compatible
  router_id                         = var.router_id
  spf_timers                        = var.spf_timers

  dynamic "area" {
    for_each = var.area
    content {
      authentication                                 = area.value["authentication"]
      default_cost                                   = area.value["default_cost"]
      id                                             = area.value["id"]
      nssa_default_information_originate             = area.value["nssa_default_information_originate"]
      nssa_default_information_originate_metric      = area.value["nssa_default_information_originate_metric"]
      nssa_default_information_originate_metric_type = area.value["nssa_default_information_originate_metric_type"]
      nssa_redistribution                            = area.value["nssa_redistribution"]
      nssa_translator_role                           = area.value["nssa_translator_role"]
      shortcut                                       = area.value["shortcut"]
      stub_type                                      = area.value["stub_type"]
      type                                           = area.value["type"]

      dynamic "filter_list" {
        for_each = area.value.filter_list
        content {
          direction = filter_list.value["direction"]
          id        = filter_list.value["id"]
          list      = filter_list.value["list"]
        }
      }

      dynamic "range" {
        for_each = area.value.range
        content {
          advertise         = range.value["advertise"]
          id                = range.value["id"]
          prefix            = range.value["prefix"]
          substitute        = range.value["substitute"]
          substitute_status = range.value["substitute_status"]
        }
      }

      dynamic "virtual_link" {
        for_each = area.value.virtual_link
        content {
          authentication      = virtual_link.value["authentication"]
          authentication_key  = virtual_link.value["authentication_key"]
          dead_interval       = virtual_link.value["dead_interval"]
          hello_interval      = virtual_link.value["hello_interval"]
          md5_key             = virtual_link.value["md5_key"]
          md5_keychain        = virtual_link.value["md5_keychain"]
          name                = virtual_link.value["name"]
          peer                = virtual_link.value["peer"]
          retransmit_interval = virtual_link.value["retransmit_interval"]
          transmit_delay      = virtual_link.value["transmit_delay"]

          dynamic "md5_keys" {
            for_each = virtual_link.value.md5_keys
            content {
              id         = md5_keys.value["id"]
              key_string = md5_keys.value["key_string"]
            }
          }

        }
      }

    }
  }

  dynamic "distribute_list" {
    for_each = var.distribute_list
    content {
      access_list = distribute_list.value["access_list"]
      id          = distribute_list.value["id"]
      protocol    = distribute_list.value["protocol"]
    }
  }

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      cost          = neighbor.value["cost"]
      id            = neighbor.value["id"]
      ip            = neighbor.value["ip"]
      poll_interval = neighbor.value["poll_interval"]
      priority      = neighbor.value["priority"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      area   = network.value["area"]
      id     = network.value["id"]
      prefix = network.value["prefix"]
    }
  }

  dynamic "ospf_interface" {
    for_each = var.ospf_interface
    content {
      authentication      = ospf_interface.value["authentication"]
      authentication_key  = ospf_interface.value["authentication_key"]
      bfd                 = ospf_interface.value["bfd"]
      cost                = ospf_interface.value["cost"]
      database_filter_out = ospf_interface.value["database_filter_out"]
      dead_interval       = ospf_interface.value["dead_interval"]
      hello_interval      = ospf_interface.value["hello_interval"]
      hello_multiplier    = ospf_interface.value["hello_multiplier"]
      interface           = ospf_interface.value["interface"]
      ip                  = ospf_interface.value["ip"]
      md5_key             = ospf_interface.value["md5_key"]
      md5_keychain        = ospf_interface.value["md5_keychain"]
      mtu                 = ospf_interface.value["mtu"]
      mtu_ignore          = ospf_interface.value["mtu_ignore"]
      name                = ospf_interface.value["name"]
      network_type        = ospf_interface.value["network_type"]
      prefix_length       = ospf_interface.value["prefix_length"]
      priority            = ospf_interface.value["priority"]
      resync_timeout      = ospf_interface.value["resync_timeout"]
      retransmit_interval = ospf_interface.value["retransmit_interval"]
      status              = ospf_interface.value["status"]
      transmit_delay      = ospf_interface.value["transmit_delay"]

      dynamic "md5_keys" {
        for_each = ospf_interface.value.md5_keys
        content {
          id         = md5_keys.value["id"]
          key_string = md5_keys.value["key_string"]
        }
      }

    }
  }

  dynamic "passive_interface" {
    for_each = var.passive_interface
    content {
      name = passive_interface.value["name"]
    }
  }

  dynamic "redistribute" {
    for_each = var.redistribute
    content {
      metric      = redistribute.value["metric"]
      metric_type = redistribute.value["metric_type"]
      name        = redistribute.value["name"]
      routemap    = redistribute.value["routemap"]
      status      = redistribute.value["status"]
      tag         = redistribute.value["tag"]
    }
  }

  dynamic "summary_address" {
    for_each = var.summary_address
    content {
      advertise = summary_address.value["advertise"]
      id        = summary_address.value["id"]
      prefix    = summary_address.value["prefix"]
      tag       = summary_address.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "abr_type" {
  description = "returns a string"
  value       = fortios_router_ospf.this.abr_type
}

output "auto_cost_ref_bandwidth" {
  description = "returns a number"
  value       = fortios_router_ospf.this.auto_cost_ref_bandwidth
}

output "bfd" {
  description = "returns a string"
  value       = fortios_router_ospf.this.bfd
}

output "database_overflow" {
  description = "returns a string"
  value       = fortios_router_ospf.this.database_overflow
}

output "database_overflow_max_lsas" {
  description = "returns a number"
  value       = fortios_router_ospf.this.database_overflow_max_lsas
}

output "database_overflow_time_to_recover" {
  description = "returns a number"
  value       = fortios_router_ospf.this.database_overflow_time_to_recover
}

output "default_information_metric" {
  description = "returns a number"
  value       = fortios_router_ospf.this.default_information_metric
}

output "default_information_metric_type" {
  description = "returns a string"
  value       = fortios_router_ospf.this.default_information_metric_type
}

output "default_information_originate" {
  description = "returns a string"
  value       = fortios_router_ospf.this.default_information_originate
}

output "default_information_route_map" {
  description = "returns a string"
  value       = fortios_router_ospf.this.default_information_route_map
}

output "default_metric" {
  description = "returns a number"
  value       = fortios_router_ospf.this.default_metric
}

output "distance" {
  description = "returns a number"
  value       = fortios_router_ospf.this.distance
}

output "distance_external" {
  description = "returns a number"
  value       = fortios_router_ospf.this.distance_external
}

output "distance_inter_area" {
  description = "returns a number"
  value       = fortios_router_ospf.this.distance_inter_area
}

output "distance_intra_area" {
  description = "returns a number"
  value       = fortios_router_ospf.this.distance_intra_area
}

output "distribute_list_in" {
  description = "returns a string"
  value       = fortios_router_ospf.this.distribute_list_in
}

output "distribute_route_map_in" {
  description = "returns a string"
  value       = fortios_router_ospf.this.distribute_route_map_in
}

output "id" {
  description = "returns a string"
  value       = fortios_router_ospf.this.id
}

output "log_neighbour_changes" {
  description = "returns a string"
  value       = fortios_router_ospf.this.log_neighbour_changes
}

output "restart_mode" {
  description = "returns a string"
  value       = fortios_router_ospf.this.restart_mode
}

output "restart_period" {
  description = "returns a number"
  value       = fortios_router_ospf.this.restart_period
}

output "rfc1583_compatible" {
  description = "returns a string"
  value       = fortios_router_ospf.this.rfc1583_compatible
}

output "spf_timers" {
  description = "returns a string"
  value       = fortios_router_ospf.this.spf_timers
}

output "this" {
  value = fortios_router_ospf.this
}
```

[top](#index)