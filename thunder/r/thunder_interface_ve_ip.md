# thunder_interface_ve_ip

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
module "thunder_interface_ve_ip" {
  source = "./modules/thunder/r/thunder_interface_ve_ip"

  # allow_promiscuous_vip - (optional) is a type of number
  allow_promiscuous_vip = null
  # client - (optional) is a type of number
  client = null
  # dhcp - (optional) is a type of number
  dhcp = null
  # generate_membership_query - (optional) is a type of number
  generate_membership_query = null
  # ifnum - (optional) is a type of number
  ifnum = null
  # inside - (optional) is a type of number
  inside = null
  # max_resp_time - (optional) is a type of number
  max_resp_time = null
  # outside - (optional) is a type of number
  outside = null
  # query_interval - (optional) is a type of number
  query_interval = null
  # server - (optional) is a type of number
  server = null
  # slb_partition_redirect - (optional) is a type of number
  slb_partition_redirect = null
  # ttl_ignore - (optional) is a type of number
  ttl_ignore = null
  # uuid - (optional) is a type of string
  uuid = null

  address_list = [{
    ipv4_address = null
    ipv4_netmask = null
  }]

  helper_address_list = [{
    helper_address = null
  }]

  ospf = [{
    ospf_global = [{
      authentication_cfg = [{
        authentication = null
        value          = null
      }]
      authentication_key = null
      bfd_cfg = [{
        bfd     = null
        disable = null
      }]
      cost = null
      database_filter_cfg = [{
        database_filter = null
        out             = null
      }]
      dead_interval  = null
      disable        = null
      hello_interval = null
      message_digest_cfg = [{
        md5 = [{
          encrypted = null
          md5_value = null
        }]
        message_digest_key = null
      }]
      mtu        = null
      mtu_ignore = null
      network = [{
        broadcast           = null
        non_broadcast       = null
        p2mp_nbma           = null
        point_to_multipoint = null
        point_to_point      = null
      }]
      priority            = null
      retransmit_interval = null
      transmit_delay      = null
      uuid                = null
    }]
    ospf_ip_list = [{
      authentication     = null
      authentication_key = null
      cost               = null
      database_filter    = null
      dead_interval      = null
      hello_interval     = null
      ip_addr            = null
      message_digest_cfg = [{
        md5 = [{
          encrypted = null
          md5_value = null
        }]
        message_digest_key = null
      }]
      mtu_ignore          = null
      out                 = null
      priority            = null
      retransmit_interval = null
      transmit_delay      = null
      uuid                = null
      value               = null
    }]
  }]

  rip = [{
    authentication = [{
      key_chain = [{
        key_chain = null
      }]
      mode = [{
        mode = null
      }]
      str = [{
        string = null
      }]
    }]
    receive_cfg = [{
      receive = null
      version = null
    }]
    receive_packet = null
    send_cfg = [{
      send    = null
      version = null
    }]
    send_packet = null
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
  }]

  stateful_firewall = [{
    access_list = null
    acl_id      = null
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
variable "allow_promiscuous_vip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dhcp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "generate_membership_query" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ifnum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "inside" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_resp_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outside" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slb_partition_redirect" {
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

variable "address_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ipv4_address = string
      ipv4_netmask = string
    }
  ))
  default = []
}

variable "helper_address_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      helper_address = string
    }
  ))
  default = []
}

variable "ospf" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ospf_global = list(object(
        {
          authentication_cfg = list(object(
            {
              authentication = number
              value          = string
            }
          ))
          authentication_key = string
          bfd_cfg = list(object(
            {
              bfd     = number
              disable = number
            }
          ))
          cost = number
          database_filter_cfg = list(object(
            {
              database_filter = string
              out             = number
            }
          ))
          dead_interval  = number
          disable        = string
          hello_interval = number
          message_digest_cfg = list(object(
            {
              md5 = list(object(
                {
                  encrypted = string
                  md5_value = string
                }
              ))
              message_digest_key = number
            }
          ))
          mtu        = number
          mtu_ignore = number
          network = list(object(
            {
              broadcast           = number
              non_broadcast       = number
              p2mp_nbma           = number
              point_to_multipoint = number
              point_to_point      = number
            }
          ))
          priority            = number
          retransmit_interval = number
          transmit_delay      = number
          uuid                = string
        }
      ))
      ospf_ip_list = list(object(
        {
          authentication     = number
          authentication_key = string
          cost               = number
          database_filter    = string
          dead_interval      = number
          hello_interval     = number
          ip_addr            = string
          message_digest_cfg = list(object(
            {
              md5 = list(object(
                {
                  encrypted = string
                  md5_value = string
                }
              ))
              message_digest_key = number
            }
          ))
          mtu_ignore          = number
          out                 = number
          priority            = number
          retransmit_interval = number
          transmit_delay      = number
          uuid                = string
          value               = string
        }
      ))
    }
  ))
  default = []
}

variable "rip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authentication = list(object(
        {
          key_chain = list(object(
            {
              key_chain = string
            }
          ))
          mode = list(object(
            {
              mode = string
            }
          ))
          str = list(object(
            {
              string = string
            }
          ))
        }
      ))
      receive_cfg = list(object(
        {
          receive = number
          version = string
        }
      ))
      receive_packet = number
      send_cfg = list(object(
        {
          send    = number
          version = string
        }
      ))
      send_packet = number
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
    }
  ))
  default = []
}

variable "stateful_firewall" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_list = number
      acl_id      = number
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
resource "thunder_interface_ve_ip" "this" {
  # allow_promiscuous_vip - (optional) is a type of number
  allow_promiscuous_vip = var.allow_promiscuous_vip
  # client - (optional) is a type of number
  client = var.client
  # dhcp - (optional) is a type of number
  dhcp = var.dhcp
  # generate_membership_query - (optional) is a type of number
  generate_membership_query = var.generate_membership_query
  # ifnum - (optional) is a type of number
  ifnum = var.ifnum
  # inside - (optional) is a type of number
  inside = var.inside
  # max_resp_time - (optional) is a type of number
  max_resp_time = var.max_resp_time
  # outside - (optional) is a type of number
  outside = var.outside
  # query_interval - (optional) is a type of number
  query_interval = var.query_interval
  # server - (optional) is a type of number
  server = var.server
  # slb_partition_redirect - (optional) is a type of number
  slb_partition_redirect = var.slb_partition_redirect
  # ttl_ignore - (optional) is a type of number
  ttl_ignore = var.ttl_ignore
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "address_list" {
    for_each = var.address_list
    content {
      # ipv4_address - (optional) is a type of string
      ipv4_address = address_list.value["ipv4_address"]
      # ipv4_netmask - (optional) is a type of string
      ipv4_netmask = address_list.value["ipv4_netmask"]
    }
  }

  dynamic "helper_address_list" {
    for_each = var.helper_address_list
    content {
      # helper_address - (optional) is a type of string
      helper_address = helper_address_list.value["helper_address"]
    }
  }

  dynamic "ospf" {
    for_each = var.ospf
    content {

      dynamic "ospf_global" {
        for_each = ospf.value.ospf_global
        content {
          # authentication_key - (optional) is a type of string
          authentication_key = ospf_global.value["authentication_key"]
          # cost - (optional) is a type of number
          cost = ospf_global.value["cost"]
          # dead_interval - (optional) is a type of number
          dead_interval = ospf_global.value["dead_interval"]
          # disable - (optional) is a type of string
          disable = ospf_global.value["disable"]
          # hello_interval - (optional) is a type of number
          hello_interval = ospf_global.value["hello_interval"]
          # mtu - (optional) is a type of number
          mtu = ospf_global.value["mtu"]
          # mtu_ignore - (optional) is a type of number
          mtu_ignore = ospf_global.value["mtu_ignore"]
          # priority - (optional) is a type of number
          priority = ospf_global.value["priority"]
          # retransmit_interval - (optional) is a type of number
          retransmit_interval = ospf_global.value["retransmit_interval"]
          # transmit_delay - (optional) is a type of number
          transmit_delay = ospf_global.value["transmit_delay"]
          # uuid - (optional) is a type of string
          uuid = ospf_global.value["uuid"]

          dynamic "authentication_cfg" {
            for_each = ospf_global.value.authentication_cfg
            content {
              # authentication - (optional) is a type of number
              authentication = authentication_cfg.value["authentication"]
              # value - (optional) is a type of string
              value = authentication_cfg.value["value"]
            }
          }

          dynamic "bfd_cfg" {
            for_each = ospf_global.value.bfd_cfg
            content {
              # bfd - (optional) is a type of number
              bfd = bfd_cfg.value["bfd"]
              # disable - (optional) is a type of number
              disable = bfd_cfg.value["disable"]
            }
          }

          dynamic "database_filter_cfg" {
            for_each = ospf_global.value.database_filter_cfg
            content {
              # database_filter - (optional) is a type of string
              database_filter = database_filter_cfg.value["database_filter"]
              # out - (optional) is a type of number
              out = database_filter_cfg.value["out"]
            }
          }

          dynamic "message_digest_cfg" {
            for_each = ospf_global.value.message_digest_cfg
            content {
              # message_digest_key - (optional) is a type of number
              message_digest_key = message_digest_cfg.value["message_digest_key"]

              dynamic "md5" {
                for_each = message_digest_cfg.value.md5
                content {
                  # encrypted - (optional) is a type of string
                  encrypted = md5.value["encrypted"]
                  # md5_value - (optional) is a type of string
                  md5_value = md5.value["md5_value"]
                }
              }

            }
          }

          dynamic "network" {
            for_each = ospf_global.value.network
            content {
              # broadcast - (optional) is a type of number
              broadcast = network.value["broadcast"]
              # non_broadcast - (optional) is a type of number
              non_broadcast = network.value["non_broadcast"]
              # p2mp_nbma - (optional) is a type of number
              p2mp_nbma = network.value["p2mp_nbma"]
              # point_to_multipoint - (optional) is a type of number
              point_to_multipoint = network.value["point_to_multipoint"]
              # point_to_point - (optional) is a type of number
              point_to_point = network.value["point_to_point"]
            }
          }

        }
      }

      dynamic "ospf_ip_list" {
        for_each = ospf.value.ospf_ip_list
        content {
          # authentication - (optional) is a type of number
          authentication = ospf_ip_list.value["authentication"]
          # authentication_key - (optional) is a type of string
          authentication_key = ospf_ip_list.value["authentication_key"]
          # cost - (optional) is a type of number
          cost = ospf_ip_list.value["cost"]
          # database_filter - (optional) is a type of string
          database_filter = ospf_ip_list.value["database_filter"]
          # dead_interval - (optional) is a type of number
          dead_interval = ospf_ip_list.value["dead_interval"]
          # hello_interval - (optional) is a type of number
          hello_interval = ospf_ip_list.value["hello_interval"]
          # ip_addr - (optional) is a type of string
          ip_addr = ospf_ip_list.value["ip_addr"]
          # mtu_ignore - (optional) is a type of number
          mtu_ignore = ospf_ip_list.value["mtu_ignore"]
          # out - (optional) is a type of number
          out = ospf_ip_list.value["out"]
          # priority - (optional) is a type of number
          priority = ospf_ip_list.value["priority"]
          # retransmit_interval - (optional) is a type of number
          retransmit_interval = ospf_ip_list.value["retransmit_interval"]
          # transmit_delay - (optional) is a type of number
          transmit_delay = ospf_ip_list.value["transmit_delay"]
          # uuid - (optional) is a type of string
          uuid = ospf_ip_list.value["uuid"]
          # value - (optional) is a type of string
          value = ospf_ip_list.value["value"]

          dynamic "message_digest_cfg" {
            for_each = ospf_ip_list.value.message_digest_cfg
            content {
              # message_digest_key - (optional) is a type of number
              message_digest_key = message_digest_cfg.value["message_digest_key"]

              dynamic "md5" {
                for_each = message_digest_cfg.value.md5
                content {
                  # encrypted - (optional) is a type of string
                  encrypted = md5.value["encrypted"]
                  # md5_value - (optional) is a type of string
                  md5_value = md5.value["md5_value"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "rip" {
    for_each = var.rip
    content {
      # receive_packet - (optional) is a type of number
      receive_packet = rip.value["receive_packet"]
      # send_packet - (optional) is a type of number
      send_packet = rip.value["send_packet"]
      # uuid - (optional) is a type of string
      uuid = rip.value["uuid"]

      dynamic "authentication" {
        for_each = rip.value.authentication
        content {

          dynamic "key_chain" {
            for_each = authentication.value.key_chain
            content {
              # key_chain - (optional) is a type of string
              key_chain = key_chain.value["key_chain"]
            }
          }

          dynamic "mode" {
            for_each = authentication.value.mode
            content {
              # mode - (optional) is a type of string
              mode = mode.value["mode"]
            }
          }

          dynamic "str" {
            for_each = authentication.value.str
            content {
              # string - (optional) is a type of string
              string = str.value["string"]
            }
          }

        }
      }

      dynamic "receive_cfg" {
        for_each = rip.value.receive_cfg
        content {
          # receive - (optional) is a type of number
          receive = receive_cfg.value["receive"]
          # version - (optional) is a type of string
          version = receive_cfg.value["version"]
        }
      }

      dynamic "send_cfg" {
        for_each = rip.value.send_cfg
        content {
          # send - (optional) is a type of number
          send = send_cfg.value["send"]
          # version - (optional) is a type of string
          version = send_cfg.value["version"]
        }
      }

      dynamic "split_horizon_cfg" {
        for_each = rip.value.split_horizon_cfg
        content {
          # state - (optional) is a type of string
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
          # tag - (optional) is a type of string
          tag = isis.value["tag"]
          # uuid - (optional) is a type of string
          uuid = isis.value["uuid"]
        }
      }

    }
  }

  dynamic "stateful_firewall" {
    for_each = var.stateful_firewall
    content {
      # access_list - (optional) is a type of number
      access_list = stateful_firewall.value["access_list"]
      # acl_id - (optional) is a type of number
      acl_id = stateful_firewall.value["acl_id"]
      # class_list - (optional) is a type of string
      class_list = stateful_firewall.value["class_list"]
      # inside - (optional) is a type of number
      inside = stateful_firewall.value["inside"]
      # outside - (optional) is a type of number
      outside = stateful_firewall.value["outside"]
      # uuid - (optional) is a type of string
      uuid = stateful_firewall.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_ve_ip.this.id
}

output "this" {
  value = thunder_interface_ve_ip.this
}
```

[top](#index)