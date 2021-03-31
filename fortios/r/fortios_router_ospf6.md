# fortios_router_ospf6

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
module "fortios_router_ospf6" {
  source = "./modules/fortios/r/fortios_router_ospf6"

  # abr_type - (optional) is a type of string
  abr_type = null
  # auto_cost_ref_bandwidth - (optional) is a type of number
  auto_cost_ref_bandwidth = null
  # bfd - (optional) is a type of string
  bfd = null
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
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # log_neighbour_changes - (optional) is a type of string
  log_neighbour_changes = null
  # router_id - (required) is a type of string
  router_id = null
  # spf_timers - (optional) is a type of string
  spf_timers = null

  area = [{
    authentication = null
    default_cost   = null
    id             = null
    ipsec_auth_alg = null
    ipsec_enc_alg  = null
    ipsec_keys = [{
      auth_key = null
      enc_key  = null
      spi      = null
    }]
    key_rollover_interval                          = null
    nssa_default_information_originate             = null
    nssa_default_information_originate_metric      = null
    nssa_default_information_originate_metric_type = null
    nssa_redistribution                            = null
    nssa_translator_role                           = null
    range = [{
      advertise = null
      id        = null
      prefix6   = null
    }]
    stub_type = null
    type      = null
    virtual_link = [{
      authentication = null
      dead_interval  = null
      hello_interval = null
      ipsec_auth_alg = null
      ipsec_enc_alg  = null
      ipsec_keys = [{
        auth_key = null
        enc_key  = null
        spi      = null
      }]
      key_rollover_interval = null
      name                  = null
      peer                  = null
      retransmit_interval   = null
      transmit_delay        = null
    }]
  }]

  ospf6_interface = [{
    area_id        = null
    authentication = null
    bfd            = null
    cost           = null
    dead_interval  = null
    hello_interval = null
    interface      = null
    ipsec_auth_alg = null
    ipsec_enc_alg  = null
    ipsec_keys = [{
      auth_key = null
      enc_key  = null
      spi      = null
    }]
    key_rollover_interval = null
    mtu                   = null
    mtu_ignore            = null
    name                  = null
    neighbor = [{
      cost          = null
      ip6           = null
      poll_interval = null
      priority      = null
    }]
    network_type        = null
    priority            = null
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
  }]

  summary_address = [{
    advertise = null
    id        = null
    prefix6   = null
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
      id             = string
      ipsec_auth_alg = string
      ipsec_enc_alg  = string
      ipsec_keys = list(object(
        {
          auth_key = string
          enc_key  = string
          spi      = number
        }
      ))
      key_rollover_interval                          = number
      nssa_default_information_originate             = string
      nssa_default_information_originate_metric      = number
      nssa_default_information_originate_metric_type = string
      nssa_redistribution                            = string
      nssa_translator_role                           = string
      range = list(object(
        {
          advertise = string
          id        = number
          prefix6   = string
        }
      ))
      stub_type = string
      type      = string
      virtual_link = list(object(
        {
          authentication = string
          dead_interval  = number
          hello_interval = number
          ipsec_auth_alg = string
          ipsec_enc_alg  = string
          ipsec_keys = list(object(
            {
              auth_key = string
              enc_key  = string
              spi      = number
            }
          ))
          key_rollover_interval = number
          name                  = string
          peer                  = string
          retransmit_interval   = number
          transmit_delay        = number
        }
      ))
    }
  ))
  default = []
}

variable "ospf6_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      area_id        = string
      authentication = string
      bfd            = string
      cost           = number
      dead_interval  = number
      hello_interval = number
      interface      = string
      ipsec_auth_alg = string
      ipsec_enc_alg  = string
      ipsec_keys = list(object(
        {
          auth_key = string
          enc_key  = string
          spi      = number
        }
      ))
      key_rollover_interval = number
      mtu                   = number
      mtu_ignore            = string
      name                  = string
      neighbor = list(object(
        {
          cost          = number
          ip6           = string
          poll_interval = number
          priority      = number
        }
      ))
      network_type        = string
      priority            = number
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
      prefix6   = string
      tag       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_ospf6" "this" {
  abr_type                        = var.abr_type
  auto_cost_ref_bandwidth         = var.auto_cost_ref_bandwidth
  bfd                             = var.bfd
  default_information_metric      = var.default_information_metric
  default_information_metric_type = var.default_information_metric_type
  default_information_originate   = var.default_information_originate
  default_information_route_map   = var.default_information_route_map
  default_metric                  = var.default_metric
  dynamic_sort_subtable           = var.dynamic_sort_subtable
  log_neighbour_changes           = var.log_neighbour_changes
  router_id                       = var.router_id
  spf_timers                      = var.spf_timers

  dynamic "area" {
    for_each = var.area
    content {
      authentication                                 = area.value["authentication"]
      default_cost                                   = area.value["default_cost"]
      id                                             = area.value["id"]
      ipsec_auth_alg                                 = area.value["ipsec_auth_alg"]
      ipsec_enc_alg                                  = area.value["ipsec_enc_alg"]
      key_rollover_interval                          = area.value["key_rollover_interval"]
      nssa_default_information_originate             = area.value["nssa_default_information_originate"]
      nssa_default_information_originate_metric      = area.value["nssa_default_information_originate_metric"]
      nssa_default_information_originate_metric_type = area.value["nssa_default_information_originate_metric_type"]
      nssa_redistribution                            = area.value["nssa_redistribution"]
      nssa_translator_role                           = area.value["nssa_translator_role"]
      stub_type                                      = area.value["stub_type"]
      type                                           = area.value["type"]

      dynamic "ipsec_keys" {
        for_each = area.value.ipsec_keys
        content {
          auth_key = ipsec_keys.value["auth_key"]
          enc_key  = ipsec_keys.value["enc_key"]
          spi      = ipsec_keys.value["spi"]
        }
      }

      dynamic "range" {
        for_each = area.value.range
        content {
          advertise = range.value["advertise"]
          id        = range.value["id"]
          prefix6   = range.value["prefix6"]
        }
      }

      dynamic "virtual_link" {
        for_each = area.value.virtual_link
        content {
          authentication        = virtual_link.value["authentication"]
          dead_interval         = virtual_link.value["dead_interval"]
          hello_interval        = virtual_link.value["hello_interval"]
          ipsec_auth_alg        = virtual_link.value["ipsec_auth_alg"]
          ipsec_enc_alg         = virtual_link.value["ipsec_enc_alg"]
          key_rollover_interval = virtual_link.value["key_rollover_interval"]
          name                  = virtual_link.value["name"]
          peer                  = virtual_link.value["peer"]
          retransmit_interval   = virtual_link.value["retransmit_interval"]
          transmit_delay        = virtual_link.value["transmit_delay"]

          dynamic "ipsec_keys" {
            for_each = virtual_link.value.ipsec_keys
            content {
              auth_key = ipsec_keys.value["auth_key"]
              enc_key  = ipsec_keys.value["enc_key"]
              spi      = ipsec_keys.value["spi"]
            }
          }

        }
      }

    }
  }

  dynamic "ospf6_interface" {
    for_each = var.ospf6_interface
    content {
      area_id               = ospf6_interface.value["area_id"]
      authentication        = ospf6_interface.value["authentication"]
      bfd                   = ospf6_interface.value["bfd"]
      cost                  = ospf6_interface.value["cost"]
      dead_interval         = ospf6_interface.value["dead_interval"]
      hello_interval        = ospf6_interface.value["hello_interval"]
      interface             = ospf6_interface.value["interface"]
      ipsec_auth_alg        = ospf6_interface.value["ipsec_auth_alg"]
      ipsec_enc_alg         = ospf6_interface.value["ipsec_enc_alg"]
      key_rollover_interval = ospf6_interface.value["key_rollover_interval"]
      mtu                   = ospf6_interface.value["mtu"]
      mtu_ignore            = ospf6_interface.value["mtu_ignore"]
      name                  = ospf6_interface.value["name"]
      network_type          = ospf6_interface.value["network_type"]
      priority              = ospf6_interface.value["priority"]
      retransmit_interval   = ospf6_interface.value["retransmit_interval"]
      status                = ospf6_interface.value["status"]
      transmit_delay        = ospf6_interface.value["transmit_delay"]

      dynamic "ipsec_keys" {
        for_each = ospf6_interface.value.ipsec_keys
        content {
          auth_key = ipsec_keys.value["auth_key"]
          enc_key  = ipsec_keys.value["enc_key"]
          spi      = ipsec_keys.value["spi"]
        }
      }

      dynamic "neighbor" {
        for_each = ospf6_interface.value.neighbor
        content {
          cost          = neighbor.value["cost"]
          ip6           = neighbor.value["ip6"]
          poll_interval = neighbor.value["poll_interval"]
          priority      = neighbor.value["priority"]
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
    }
  }

  dynamic "summary_address" {
    for_each = var.summary_address
    content {
      advertise = summary_address.value["advertise"]
      id        = summary_address.value["id"]
      prefix6   = summary_address.value["prefix6"]
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
  value       = fortios_router_ospf6.this.abr_type
}

output "auto_cost_ref_bandwidth" {
  description = "returns a number"
  value       = fortios_router_ospf6.this.auto_cost_ref_bandwidth
}

output "bfd" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.bfd
}

output "default_information_metric" {
  description = "returns a number"
  value       = fortios_router_ospf6.this.default_information_metric
}

output "default_information_metric_type" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.default_information_metric_type
}

output "default_information_originate" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.default_information_originate
}

output "default_information_route_map" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.default_information_route_map
}

output "default_metric" {
  description = "returns a number"
  value       = fortios_router_ospf6.this.default_metric
}

output "id" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.id
}

output "log_neighbour_changes" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.log_neighbour_changes
}

output "spf_timers" {
  description = "returns a string"
  value       = fortios_router_ospf6.this.spf_timers
}

output "this" {
  value = fortios_router_ospf6.this
}
```

[top](#index)