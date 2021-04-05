# thunder_interface_ve_ipv6

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_interface_ve_ipv6" {
  source = "./modules/thunder/r/thunder_interface_ve_ipv6"

  # ifnum - (optional) is a type of number
  ifnum = null
  # inbound - (optional) is a type of number
  inbound = null
  # inside - (optional) is a type of number
  inside = null
  # ipv6_enable - (optional) is a type of number
  ipv6_enable = null
  # outside - (optional) is a type of number
  outside = null
  # ttl_ignore - (optional) is a type of number
  ttl_ignore = null
  # uuid - (optional) is a type of string
  uuid = null
  # v6_acl_name - (optional) is a type of string
  v6_acl_name = null

  address_list = [{
    address_type = null
    ipv6_addr    = null
  }]

  ospf = [{
    bfd = null
    cost_cfg = [{
      cost        = null
      instance_id = null
    }]
    dead_interval_cfg = [{
      dead_interval = null
      instance_id   = null
    }]
    disable = null
    hello_interval_cfg = [{
      hello_interval = null
      instance_id    = null
    }]
    mtu_ignore_cfg = [{
      instance_id = null
      mtu_ignore  = null
    }]
    neighbor_cfg = [{
      neig_inst              = null
      neighbor               = null
      neighbor_cost          = null
      neighbor_poll_interval = null
      neighbor_priority      = null
    }]
    network_list = [{
      broadcast_type      = null
      network_instance_id = null
      p2mp_nbma           = null
    }]
    priority_cfg = [{
      instance_id = null
      priority    = null
    }]
    retransmit_interval_cfg = [{
      instance_id         = null
      retransmit_interval = null
    }]
    transmit_delay_cfg = [{
      instance_id    = null
      transmit_delay = null
    }]
    uuid = null
  }]

  rip = [{
    split_horizon_cfg = [{
      state = null
    }]
    uuid = null
  }]

  router = [{
    isis = [{
      tag  = null
      uuid = null
    }]
    ospf = [{
      area_list = [{
        area_id_addr = null
        area_id_num  = null
        instance_id  = null
        tag          = null
      }]
      uuid = null
    }]
    ripng = [{
      rip  = null
      uuid = null
    }]
  }]

  router_adver = [{
    action                   = null
    adver_mtu                = null
    adver_mtu_disable        = null
    adver_vrid               = null
    adver_vrid_default       = null
    default_lifetime         = null
    floating_ip              = null
    floating_ip_default_vrid = null
    hop_limit                = null
    managed_config_action    = null
    max_interval             = null
    min_interval             = null
    other_config_action      = null
    prefix_list = [{
      not_autonomous     = null
      not_on_link        = null
      preferred_lifetime = null
      prefix             = null
      valid_lifetime     = null
    }]
    rate_limit                   = null
    reachable_time               = null
    retransmit_timer             = null
    use_floating_ip              = null
    use_floating_ip_default_vrid = null
  }]

  stateful_firewall = [{
    access_list = null
    acl_name    = null
    class_list  = null
    inside      = null
    outside     = null
    uuid        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ifnum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "inbound" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "inside" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outside" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ttl_ignore" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "v6_acl_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      address_type = string
      ipv6_addr    = string
    }
  ))
  default = []
}

variable "ospf" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bfd = number
      cost_cfg = list(object(
        {
          cost        = number
          instance_id = number
        }
      ))
      dead_interval_cfg = list(object(
        {
          dead_interval = number
          instance_id   = number
        }
      ))
      disable = number
      hello_interval_cfg = list(object(
        {
          hello_interval = number
          instance_id    = number
        }
      ))
      mtu_ignore_cfg = list(object(
        {
          instance_id = number
          mtu_ignore  = number
        }
      ))
      neighbor_cfg = list(object(
        {
          neig_inst              = number
          neighbor               = string
          neighbor_cost          = number
          neighbor_poll_interval = number
          neighbor_priority      = number
        }
      ))
      network_list = list(object(
        {
          broadcast_type      = string
          network_instance_id = number
          p2mp_nbma           = number
        }
      ))
      priority_cfg = list(object(
        {
          instance_id = number
          priority    = number
        }
      ))
      retransmit_interval_cfg = list(object(
        {
          instance_id         = number
          retransmit_interval = number
        }
      ))
      transmit_delay_cfg = list(object(
        {
          instance_id    = number
          transmit_delay = number
        }
      ))
      uuid = string
    }
  ))
  default = []
}

variable "rip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      split_horizon_cfg = list(object(
        {
          state = string
        }
      ))
      uuid = string
    }
  ))
  default = []
}

variable "router" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      isis = list(object(
        {
          tag  = string
          uuid = string
        }
      ))
      ospf = list(object(
        {
          area_list = list(object(
            {
              area_id_addr = string
              area_id_num  = number
              instance_id  = number
              tag          = string
            }
          ))
          uuid = string
        }
      ))
      ripng = list(object(
        {
          rip  = number
          uuid = string
        }
      ))
    }
  ))
  default = []
}

variable "router_adver" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action                   = string
      adver_mtu                = number
      adver_mtu_disable        = number
      adver_vrid               = number
      adver_vrid_default       = number
      default_lifetime         = number
      floating_ip              = string
      floating_ip_default_vrid = string
      hop_limit                = number
      managed_config_action    = string
      max_interval             = number
      min_interval             = number
      other_config_action      = string
      prefix_list = list(object(
        {
          not_autonomous     = number
          not_on_link        = number
          preferred_lifetime = number
          prefix             = string
          valid_lifetime     = number
        }
      ))
      rate_limit                   = number
      reachable_time               = number
      retransmit_timer             = number
      use_floating_ip              = number
      use_floating_ip_default_vrid = number
    }
  ))
  default = []
}

variable "stateful_firewall" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_list = number
      acl_name    = string
      class_list  = string
      inside      = number
      outside     = number
      uuid        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_interface_ve_ipv6" "this" {
  ifnum       = var.ifnum
  inbound     = var.inbound
  inside      = var.inside
  ipv6_enable = var.ipv6_enable
  outside     = var.outside
  ttl_ignore  = var.ttl_ignore
  uuid        = var.uuid
  v6_acl_name = var.v6_acl_name

  dynamic "address_list" {
    for_each = var.address_list
    content {
      address_type = address_list.value["address_type"]
      ipv6_addr    = address_list.value["ipv6_addr"]
    }
  }

  dynamic "ospf" {
    for_each = var.ospf
    content {
      bfd     = ospf.value["bfd"]
      disable = ospf.value["disable"]
      uuid    = ospf.value["uuid"]

      dynamic "cost_cfg" {
        for_each = ospf.value.cost_cfg
        content {
          cost        = cost_cfg.value["cost"]
          instance_id = cost_cfg.value["instance_id"]
        }
      }

      dynamic "dead_interval_cfg" {
        for_each = ospf.value.dead_interval_cfg
        content {
          dead_interval = dead_interval_cfg.value["dead_interval"]
          instance_id   = dead_interval_cfg.value["instance_id"]
        }
      }

      dynamic "hello_interval_cfg" {
        for_each = ospf.value.hello_interval_cfg
        content {
          hello_interval = hello_interval_cfg.value["hello_interval"]
          instance_id    = hello_interval_cfg.value["instance_id"]
        }
      }

      dynamic "mtu_ignore_cfg" {
        for_each = ospf.value.mtu_ignore_cfg
        content {
          instance_id = mtu_ignore_cfg.value["instance_id"]
          mtu_ignore  = mtu_ignore_cfg.value["mtu_ignore"]
        }
      }

      dynamic "neighbor_cfg" {
        for_each = ospf.value.neighbor_cfg
        content {
          neig_inst              = neighbor_cfg.value["neig_inst"]
          neighbor               = neighbor_cfg.value["neighbor"]
          neighbor_cost          = neighbor_cfg.value["neighbor_cost"]
          neighbor_poll_interval = neighbor_cfg.value["neighbor_poll_interval"]
          neighbor_priority      = neighbor_cfg.value["neighbor_priority"]
        }
      }

      dynamic "network_list" {
        for_each = ospf.value.network_list
        content {
          broadcast_type      = network_list.value["broadcast_type"]
          network_instance_id = network_list.value["network_instance_id"]
          p2mp_nbma           = network_list.value["p2mp_nbma"]
        }
      }

      dynamic "priority_cfg" {
        for_each = ospf.value.priority_cfg
        content {
          instance_id = priority_cfg.value["instance_id"]
          priority    = priority_cfg.value["priority"]
        }
      }

      dynamic "retransmit_interval_cfg" {
        for_each = ospf.value.retransmit_interval_cfg
        content {
          instance_id         = retransmit_interval_cfg.value["instance_id"]
          retransmit_interval = retransmit_interval_cfg.value["retransmit_interval"]
        }
      }

      dynamic "transmit_delay_cfg" {
        for_each = ospf.value.transmit_delay_cfg
        content {
          instance_id    = transmit_delay_cfg.value["instance_id"]
          transmit_delay = transmit_delay_cfg.value["transmit_delay"]
        }
      }

    }
  }

  dynamic "rip" {
    for_each = var.rip
    content {
      uuid = rip.value["uuid"]

      dynamic "split_horizon_cfg" {
        for_each = rip.value.split_horizon_cfg
        content {
          state = split_horizon_cfg.value["state"]
        }
      }

    }
  }

  dynamic "router" {
    for_each = var.router
    content {

      dynamic "isis" {
        for_each = router.value.isis
        content {
          tag  = isis.value["tag"]
          uuid = isis.value["uuid"]
        }
      }

      dynamic "ospf" {
        for_each = router.value.ospf
        content {
          uuid = ospf.value["uuid"]

          dynamic "area_list" {
            for_each = ospf.value.area_list
            content {
              area_id_addr = area_list.value["area_id_addr"]
              area_id_num  = area_list.value["area_id_num"]
              instance_id  = area_list.value["instance_id"]
              tag          = area_list.value["tag"]
            }
          }

        }
      }

      dynamic "ripng" {
        for_each = router.value.ripng
        content {
          rip  = ripng.value["rip"]
          uuid = ripng.value["uuid"]
        }
      }

    }
  }

  dynamic "router_adver" {
    for_each = var.router_adver
    content {
      action                       = router_adver.value["action"]
      adver_mtu                    = router_adver.value["adver_mtu"]
      adver_mtu_disable            = router_adver.value["adver_mtu_disable"]
      adver_vrid                   = router_adver.value["adver_vrid"]
      adver_vrid_default           = router_adver.value["adver_vrid_default"]
      default_lifetime             = router_adver.value["default_lifetime"]
      floating_ip                  = router_adver.value["floating_ip"]
      floating_ip_default_vrid     = router_adver.value["floating_ip_default_vrid"]
      hop_limit                    = router_adver.value["hop_limit"]
      managed_config_action        = router_adver.value["managed_config_action"]
      max_interval                 = router_adver.value["max_interval"]
      min_interval                 = router_adver.value["min_interval"]
      other_config_action          = router_adver.value["other_config_action"]
      rate_limit                   = router_adver.value["rate_limit"]
      reachable_time               = router_adver.value["reachable_time"]
      retransmit_timer             = router_adver.value["retransmit_timer"]
      use_floating_ip              = router_adver.value["use_floating_ip"]
      use_floating_ip_default_vrid = router_adver.value["use_floating_ip_default_vrid"]

      dynamic "prefix_list" {
        for_each = router_adver.value.prefix_list
        content {
          not_autonomous     = prefix_list.value["not_autonomous"]
          not_on_link        = prefix_list.value["not_on_link"]
          preferred_lifetime = prefix_list.value["preferred_lifetime"]
          prefix             = prefix_list.value["prefix"]
          valid_lifetime     = prefix_list.value["valid_lifetime"]
        }
      }

    }
  }

  dynamic "stateful_firewall" {
    for_each = var.stateful_firewall
    content {
      access_list = stateful_firewall.value["access_list"]
      acl_name    = stateful_firewall.value["acl_name"]
      class_list  = stateful_firewall.value["class_list"]
      inside      = stateful_firewall.value["inside"]
      outside     = stateful_firewall.value["outside"]
      uuid        = stateful_firewall.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_ve_ipv6.this.id
}

output "this" {
  value = thunder_interface_ve_ipv6.this
}
```

[top](#index)