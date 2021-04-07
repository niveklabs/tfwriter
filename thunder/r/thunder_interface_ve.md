# thunder_interface_ve

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
module "thunder_interface_ve" {
  source = "./modules/thunder/r/thunder_interface_ve"

  # action - (optional) is a type of string
  action = null
  # ifnum - (optional) is a type of number
  ifnum = null
  # l3_vlan_fwd_disable - (optional) is a type of number
  l3_vlan_fwd_disable = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (optional) is a type of string
  name = null
  # trap_source - (optional) is a type of number
  trap_source = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  access_list = [{
    acl_id   = null
    acl_name = null
  }]

  bfd = [{
    authentication = [{
      encrypted = null
      key_id    = null
      method    = null
      password  = null
    }]
    demand = null
    echo   = null
    interval_cfg = [{
      interval   = null
      min_rx     = null
      multiplier = null
    }]
    uuid = null
  }]

  ddos = [{
    inside  = null
    outside = null
    uuid    = null
  }]

  icmp_rate_limit = [{
    lockup        = null
    lockup_period = null
    normal        = null
  }]

  icmpv6_rate_limit = [{
    lockup_period_v6 = null
    lockup_v6        = null
    normal_v6        = null
  }]

  ip = [{
    address_list = [{
      address_type = null
      ipv6_addr    = null
    }]
    allow_promiscuous_vip     = null
    client                    = null
    dhcp                      = null
    generate_membership_query = null
    helper_address_list = [{
      helper_address = null
    }]
    inside        = null
    max_resp_time = null
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
    outside        = null
    query_interval = null
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
    server                 = null
    slb_partition_redirect = null
    stateful_firewall = [{
      access_list = null
      acl_id      = null
      class_list  = null
      inside      = null
      outside     = null
      uuid        = null
    }]
    ttl_ignore = null
    uuid       = null
  }]

  ipv6 = [{
    address_list = [{
      address_type = null
      ipv6_addr    = null
    }]
    inbound     = null
    inside      = null
    ipv6_enable = null
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
    outside = null
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
    ttl_ignore  = null
    uuid        = null
    v6_acl_name = null
  }]

  isis = [{
    authentication = [{
      key_chain_list = [{
        key_chain = null
        level     = null
      }]
      mode_list = [{
        level = null
        mode  = null
      }]
      send_only_list = [{
        level     = null
        send_only = null
      }]
    }]
    bfd_cfg = [{
      bfd     = null
      disable = null
    }]
    circuit_type = null
    csnp_interval_list = [{
      csnp_interval = null
      level         = null
    }]
    hello_interval_list = [{
      hello_interval = null
      level          = null
    }]
    hello_interval_minimal_list = [{
      hello_interval_minimal = null
      level                  = null
    }]
    hello_multiplier_list = [{
      hello_multiplier = null
      level            = null
    }]
    lsp_interval = null
    mesh_group = [{
      blocked = null
      value   = null
    }]
    metric_list = [{
      level  = null
      metric = null
    }]
    network = null
    padding = null
    password_list = [{
      level    = null
      password = null
    }]
    priority_list = [{
      level    = null
      priority = null
    }]
    retransmit_interval = null
    uuid                = null
    wide_metric_list = [{
      level       = null
      wide_metric = null
    }]
  }]

  lw_4o6 = [{
    inside  = null
    outside = null
    uuid    = null
  }]

  map = [{
    inside        = null
    map_t_inside  = null
    map_t_outside = null
    outside       = null
    uuid          = null
  }]

  nptv6 = [{
    domain_list = [{
      bind_type   = null
      domain_name = null
      uuid        = null
    }]
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ifnum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l3_vlan_fwd_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trap_source" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_list" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      acl_id   = number
      acl_name = string
    }
  ))
  default = []
}

variable "bfd" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authentication = list(object(
        {
          encrypted = string
          key_id    = number
          method    = string
          password  = string
        }
      ))
      demand = number
      echo   = number
      interval_cfg = list(object(
        {
          interval   = number
          min_rx     = number
          multiplier = number
        }
      ))
      uuid = string
    }
  ))
  default = []
}

variable "ddos" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inside  = number
      outside = number
      uuid    = string
    }
  ))
  default = []
}

variable "icmp_rate_limit" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      lockup        = number
      lockup_period = number
      normal        = number
    }
  ))
  default = []
}

variable "icmpv6_rate_limit" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      lockup_period_v6 = number
      lockup_v6        = number
      normal_v6        = number
    }
  ))
  default = []
}

variable "ip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address_list = list(object(
        {
          address_type = string
          ipv6_addr    = string
        }
      ))
      allow_promiscuous_vip     = number
      client                    = number
      dhcp                      = number
      generate_membership_query = number
      helper_address_list = list(object(
        {
          helper_address = string
        }
      ))
      inside        = number
      max_resp_time = number
      ospf = list(object(
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
      outside        = number
      query_interval = number
      rip = list(object(
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
      router = list(object(
        {
          isis = list(object(
            {
              tag  = string
              uuid = string
            }
          ))
        }
      ))
      server                 = number
      slb_partition_redirect = number
      stateful_firewall = list(object(
        {
          access_list = number
          acl_id      = number
          class_list  = string
          inside      = number
          outside     = number
          uuid        = string
        }
      ))
      ttl_ignore = number
      uuid       = string
    }
  ))
  default = []
}

variable "ipv6" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address_list = list(object(
        {
          address_type = string
          ipv6_addr    = string
        }
      ))
      inbound     = number
      inside      = number
      ipv6_enable = number
      ospf = list(object(
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
      outside = number
      rip = list(object(
        {
          split_horizon_cfg = list(object(
            {
              state = string
            }
          ))
          uuid = string
        }
      ))
      router = list(object(
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
      router_adver = list(object(
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
      stateful_firewall = list(object(
        {
          access_list = number
          acl_name    = string
          class_list  = string
          inside      = number
          outside     = number
          uuid        = string
        }
      ))
      ttl_ignore  = number
      uuid        = string
      v6_acl_name = string
    }
  ))
  default = []
}

variable "isis" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authentication = list(object(
        {
          key_chain_list = list(object(
            {
              key_chain = string
              level     = string
            }
          ))
          mode_list = list(object(
            {
              level = string
              mode  = string
            }
          ))
          send_only_list = list(object(
            {
              level     = string
              send_only = number
            }
          ))
        }
      ))
      bfd_cfg = list(object(
        {
          bfd     = number
          disable = number
        }
      ))
      circuit_type = string
      csnp_interval_list = list(object(
        {
          csnp_interval = number
          level         = string
        }
      ))
      hello_interval_list = list(object(
        {
          hello_interval = number
          level          = string
        }
      ))
      hello_interval_minimal_list = list(object(
        {
          hello_interval_minimal = number
          level                  = string
        }
      ))
      hello_multiplier_list = list(object(
        {
          hello_multiplier = number
          level            = string
        }
      ))
      lsp_interval = number
      mesh_group = list(object(
        {
          blocked = number
          value   = number
        }
      ))
      metric_list = list(object(
        {
          level  = string
          metric = number
        }
      ))
      network = string
      padding = number
      password_list = list(object(
        {
          level    = string
          password = string
        }
      ))
      priority_list = list(object(
        {
          level    = string
          priority = number
        }
      ))
      retransmit_interval = number
      uuid                = string
      wide_metric_list = list(object(
        {
          level       = string
          wide_metric = number
        }
      ))
    }
  ))
  default = []
}

variable "lw_4o6" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inside  = number
      outside = number
      uuid    = string
    }
  ))
  default = []
}

variable "map" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      inside        = number
      map_t_inside  = number
      map_t_outside = number
      outside       = number
      uuid          = string
    }
  ))
  default = []
}

variable "nptv6" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      domain_list = list(object(
        {
          bind_type   = string
          domain_name = string
          uuid        = string
        }
      ))
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_interface_ve" "this" {
  # action - (optional) is a type of string
  action = var.action
  # ifnum - (optional) is a type of number
  ifnum = var.ifnum
  # l3_vlan_fwd_disable - (optional) is a type of number
  l3_vlan_fwd_disable = var.l3_vlan_fwd_disable
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (optional) is a type of string
  name = var.name
  # trap_source - (optional) is a type of number
  trap_source = var.trap_source
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "access_list" {
    for_each = var.access_list
    content {
      # acl_id - (optional) is a type of number
      acl_id = access_list.value["acl_id"]
      # acl_name - (optional) is a type of string
      acl_name = access_list.value["acl_name"]
    }
  }

  dynamic "bfd" {
    for_each = var.bfd
    content {
      # demand - (optional) is a type of number
      demand = bfd.value["demand"]
      # echo - (optional) is a type of number
      echo = bfd.value["echo"]
      # uuid - (optional) is a type of string
      uuid = bfd.value["uuid"]

      dynamic "authentication" {
        for_each = bfd.value.authentication
        content {
          # encrypted - (optional) is a type of string
          encrypted = authentication.value["encrypted"]
          # key_id - (optional) is a type of number
          key_id = authentication.value["key_id"]
          # method - (optional) is a type of string
          method = authentication.value["method"]
          # password - (optional) is a type of string
          password = authentication.value["password"]
        }
      }

      dynamic "interval_cfg" {
        for_each = bfd.value.interval_cfg
        content {
          # interval - (optional) is a type of number
          interval = interval_cfg.value["interval"]
          # min_rx - (optional) is a type of number
          min_rx = interval_cfg.value["min_rx"]
          # multiplier - (optional) is a type of number
          multiplier = interval_cfg.value["multiplier"]
        }
      }

    }
  }

  dynamic "ddos" {
    for_each = var.ddos
    content {
      # inside - (optional) is a type of number
      inside = ddos.value["inside"]
      # outside - (optional) is a type of number
      outside = ddos.value["outside"]
      # uuid - (optional) is a type of string
      uuid = ddos.value["uuid"]
    }
  }

  dynamic "icmp_rate_limit" {
    for_each = var.icmp_rate_limit
    content {
      # lockup - (optional) is a type of number
      lockup = icmp_rate_limit.value["lockup"]
      # lockup_period - (optional) is a type of number
      lockup_period = icmp_rate_limit.value["lockup_period"]
      # normal - (optional) is a type of number
      normal = icmp_rate_limit.value["normal"]
    }
  }

  dynamic "icmpv6_rate_limit" {
    for_each = var.icmpv6_rate_limit
    content {
      # lockup_period_v6 - (optional) is a type of number
      lockup_period_v6 = icmpv6_rate_limit.value["lockup_period_v6"]
      # lockup_v6 - (optional) is a type of number
      lockup_v6 = icmpv6_rate_limit.value["lockup_v6"]
      # normal_v6 - (optional) is a type of number
      normal_v6 = icmpv6_rate_limit.value["normal_v6"]
    }
  }

  dynamic "ip" {
    for_each = var.ip
    content {
      # allow_promiscuous_vip - (optional) is a type of number
      allow_promiscuous_vip = ip.value["allow_promiscuous_vip"]
      # client - (optional) is a type of number
      client = ip.value["client"]
      # dhcp - (optional) is a type of number
      dhcp = ip.value["dhcp"]
      # generate_membership_query - (optional) is a type of number
      generate_membership_query = ip.value["generate_membership_query"]
      # inside - (optional) is a type of number
      inside = ip.value["inside"]
      # max_resp_time - (optional) is a type of number
      max_resp_time = ip.value["max_resp_time"]
      # outside - (optional) is a type of number
      outside = ip.value["outside"]
      # query_interval - (optional) is a type of number
      query_interval = ip.value["query_interval"]
      # server - (optional) is a type of number
      server = ip.value["server"]
      # slb_partition_redirect - (optional) is a type of number
      slb_partition_redirect = ip.value["slb_partition_redirect"]
      # ttl_ignore - (optional) is a type of number
      ttl_ignore = ip.value["ttl_ignore"]
      # uuid - (optional) is a type of string
      uuid = ip.value["uuid"]

      dynamic "address_list" {
        for_each = ip.value.address_list
        content {
          # address_type - (optional) is a type of string
          address_type = address_list.value["address_type"]
          # ipv6_addr - (optional) is a type of string
          ipv6_addr = address_list.value["ipv6_addr"]
        }
      }

      dynamic "helper_address_list" {
        for_each = ip.value.helper_address_list
        content {
          # helper_address - (optional) is a type of string
          helper_address = helper_address_list.value["helper_address"]
        }
      }

      dynamic "ospf" {
        for_each = ip.value.ospf
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
        for_each = ip.value.rip
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
        for_each = ip.value.router
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
        for_each = ip.value.stateful_firewall
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
  }

  dynamic "ipv6" {
    for_each = var.ipv6
    content {
      # inbound - (optional) is a type of number
      inbound = ipv6.value["inbound"]
      # inside - (optional) is a type of number
      inside = ipv6.value["inside"]
      # ipv6_enable - (optional) is a type of number
      ipv6_enable = ipv6.value["ipv6_enable"]
      # outside - (optional) is a type of number
      outside = ipv6.value["outside"]
      # ttl_ignore - (optional) is a type of number
      ttl_ignore = ipv6.value["ttl_ignore"]
      # uuid - (optional) is a type of string
      uuid = ipv6.value["uuid"]
      # v6_acl_name - (optional) is a type of string
      v6_acl_name = ipv6.value["v6_acl_name"]

      dynamic "address_list" {
        for_each = ipv6.value.address_list
        content {
          # address_type - (optional) is a type of string
          address_type = address_list.value["address_type"]
          # ipv6_addr - (optional) is a type of string
          ipv6_addr = address_list.value["ipv6_addr"]
        }
      }

      dynamic "ospf" {
        for_each = ipv6.value.ospf
        content {
          # bfd - (optional) is a type of number
          bfd = ospf.value["bfd"]
          # disable - (optional) is a type of number
          disable = ospf.value["disable"]
          # uuid - (optional) is a type of string
          uuid = ospf.value["uuid"]

          dynamic "cost_cfg" {
            for_each = ospf.value.cost_cfg
            content {
              # cost - (optional) is a type of number
              cost = cost_cfg.value["cost"]
              # instance_id - (optional) is a type of number
              instance_id = cost_cfg.value["instance_id"]
            }
          }

          dynamic "dead_interval_cfg" {
            for_each = ospf.value.dead_interval_cfg
            content {
              # dead_interval - (optional) is a type of number
              dead_interval = dead_interval_cfg.value["dead_interval"]
              # instance_id - (optional) is a type of number
              instance_id = dead_interval_cfg.value["instance_id"]
            }
          }

          dynamic "hello_interval_cfg" {
            for_each = ospf.value.hello_interval_cfg
            content {
              # hello_interval - (optional) is a type of number
              hello_interval = hello_interval_cfg.value["hello_interval"]
              # instance_id - (optional) is a type of number
              instance_id = hello_interval_cfg.value["instance_id"]
            }
          }

          dynamic "mtu_ignore_cfg" {
            for_each = ospf.value.mtu_ignore_cfg
            content {
              # instance_id - (optional) is a type of number
              instance_id = mtu_ignore_cfg.value["instance_id"]
              # mtu_ignore - (optional) is a type of number
              mtu_ignore = mtu_ignore_cfg.value["mtu_ignore"]
            }
          }

          dynamic "neighbor_cfg" {
            for_each = ospf.value.neighbor_cfg
            content {
              # neig_inst - (optional) is a type of number
              neig_inst = neighbor_cfg.value["neig_inst"]
              # neighbor - (optional) is a type of string
              neighbor = neighbor_cfg.value["neighbor"]
              # neighbor_cost - (optional) is a type of number
              neighbor_cost = neighbor_cfg.value["neighbor_cost"]
              # neighbor_poll_interval - (optional) is a type of number
              neighbor_poll_interval = neighbor_cfg.value["neighbor_poll_interval"]
              # neighbor_priority - (optional) is a type of number
              neighbor_priority = neighbor_cfg.value["neighbor_priority"]
            }
          }

          dynamic "network_list" {
            for_each = ospf.value.network_list
            content {
              # broadcast_type - (optional) is a type of string
              broadcast_type = network_list.value["broadcast_type"]
              # network_instance_id - (optional) is a type of number
              network_instance_id = network_list.value["network_instance_id"]
              # p2mp_nbma - (optional) is a type of number
              p2mp_nbma = network_list.value["p2mp_nbma"]
            }
          }

          dynamic "priority_cfg" {
            for_each = ospf.value.priority_cfg
            content {
              # instance_id - (optional) is a type of number
              instance_id = priority_cfg.value["instance_id"]
              # priority - (optional) is a type of number
              priority = priority_cfg.value["priority"]
            }
          }

          dynamic "retransmit_interval_cfg" {
            for_each = ospf.value.retransmit_interval_cfg
            content {
              # instance_id - (optional) is a type of number
              instance_id = retransmit_interval_cfg.value["instance_id"]
              # retransmit_interval - (optional) is a type of number
              retransmit_interval = retransmit_interval_cfg.value["retransmit_interval"]
            }
          }

          dynamic "transmit_delay_cfg" {
            for_each = ospf.value.transmit_delay_cfg
            content {
              # instance_id - (optional) is a type of number
              instance_id = transmit_delay_cfg.value["instance_id"]
              # transmit_delay - (optional) is a type of number
              transmit_delay = transmit_delay_cfg.value["transmit_delay"]
            }
          }

        }
      }

      dynamic "rip" {
        for_each = ipv6.value.rip
        content {
          # uuid - (optional) is a type of string
          uuid = rip.value["uuid"]

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
        for_each = ipv6.value.router
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

          dynamic "ospf" {
            for_each = router.value.ospf
            content {
              # uuid - (optional) is a type of string
              uuid = ospf.value["uuid"]

              dynamic "area_list" {
                for_each = ospf.value.area_list
                content {
                  # area_id_addr - (optional) is a type of string
                  area_id_addr = area_list.value["area_id_addr"]
                  # area_id_num - (optional) is a type of number
                  area_id_num = area_list.value["area_id_num"]
                  # instance_id - (optional) is a type of number
                  instance_id = area_list.value["instance_id"]
                  # tag - (optional) is a type of string
                  tag = area_list.value["tag"]
                }
              }

            }
          }

          dynamic "ripng" {
            for_each = router.value.ripng
            content {
              # rip - (optional) is a type of number
              rip = ripng.value["rip"]
              # uuid - (optional) is a type of string
              uuid = ripng.value["uuid"]
            }
          }

        }
      }

      dynamic "router_adver" {
        for_each = ipv6.value.router_adver
        content {
          # action - (optional) is a type of string
          action = router_adver.value["action"]
          # adver_mtu - (optional) is a type of number
          adver_mtu = router_adver.value["adver_mtu"]
          # adver_mtu_disable - (optional) is a type of number
          adver_mtu_disable = router_adver.value["adver_mtu_disable"]
          # adver_vrid - (optional) is a type of number
          adver_vrid = router_adver.value["adver_vrid"]
          # adver_vrid_default - (optional) is a type of number
          adver_vrid_default = router_adver.value["adver_vrid_default"]
          # default_lifetime - (optional) is a type of number
          default_lifetime = router_adver.value["default_lifetime"]
          # floating_ip - (optional) is a type of string
          floating_ip = router_adver.value["floating_ip"]
          # floating_ip_default_vrid - (optional) is a type of string
          floating_ip_default_vrid = router_adver.value["floating_ip_default_vrid"]
          # hop_limit - (optional) is a type of number
          hop_limit = router_adver.value["hop_limit"]
          # managed_config_action - (optional) is a type of string
          managed_config_action = router_adver.value["managed_config_action"]
          # max_interval - (optional) is a type of number
          max_interval = router_adver.value["max_interval"]
          # min_interval - (optional) is a type of number
          min_interval = router_adver.value["min_interval"]
          # other_config_action - (optional) is a type of string
          other_config_action = router_adver.value["other_config_action"]
          # rate_limit - (optional) is a type of number
          rate_limit = router_adver.value["rate_limit"]
          # reachable_time - (optional) is a type of number
          reachable_time = router_adver.value["reachable_time"]
          # retransmit_timer - (optional) is a type of number
          retransmit_timer = router_adver.value["retransmit_timer"]
          # use_floating_ip - (optional) is a type of number
          use_floating_ip = router_adver.value["use_floating_ip"]
          # use_floating_ip_default_vrid - (optional) is a type of number
          use_floating_ip_default_vrid = router_adver.value["use_floating_ip_default_vrid"]

          dynamic "prefix_list" {
            for_each = router_adver.value.prefix_list
            content {
              # not_autonomous - (optional) is a type of number
              not_autonomous = prefix_list.value["not_autonomous"]
              # not_on_link - (optional) is a type of number
              not_on_link = prefix_list.value["not_on_link"]
              # preferred_lifetime - (optional) is a type of number
              preferred_lifetime = prefix_list.value["preferred_lifetime"]
              # prefix - (optional) is a type of string
              prefix = prefix_list.value["prefix"]
              # valid_lifetime - (optional) is a type of number
              valid_lifetime = prefix_list.value["valid_lifetime"]
            }
          }

        }
      }

      dynamic "stateful_firewall" {
        for_each = ipv6.value.stateful_firewall
        content {
          # access_list - (optional) is a type of number
          access_list = stateful_firewall.value["access_list"]
          # acl_name - (optional) is a type of string
          acl_name = stateful_firewall.value["acl_name"]
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
  }

  dynamic "isis" {
    for_each = var.isis
    content {
      # circuit_type - (optional) is a type of string
      circuit_type = isis.value["circuit_type"]
      # lsp_interval - (optional) is a type of number
      lsp_interval = isis.value["lsp_interval"]
      # network - (optional) is a type of string
      network = isis.value["network"]
      # padding - (optional) is a type of number
      padding = isis.value["padding"]
      # retransmit_interval - (optional) is a type of number
      retransmit_interval = isis.value["retransmit_interval"]
      # uuid - (optional) is a type of string
      uuid = isis.value["uuid"]

      dynamic "authentication" {
        for_each = isis.value.authentication
        content {

          dynamic "key_chain_list" {
            for_each = authentication.value.key_chain_list
            content {
              # key_chain - (optional) is a type of string
              key_chain = key_chain_list.value["key_chain"]
              # level - (optional) is a type of string
              level = key_chain_list.value["level"]
            }
          }

          dynamic "mode_list" {
            for_each = authentication.value.mode_list
            content {
              # level - (optional) is a type of string
              level = mode_list.value["level"]
              # mode - (optional) is a type of string
              mode = mode_list.value["mode"]
            }
          }

          dynamic "send_only_list" {
            for_each = authentication.value.send_only_list
            content {
              # level - (optional) is a type of string
              level = send_only_list.value["level"]
              # send_only - (optional) is a type of number
              send_only = send_only_list.value["send_only"]
            }
          }

        }
      }

      dynamic "bfd_cfg" {
        for_each = isis.value.bfd_cfg
        content {
          # bfd - (optional) is a type of number
          bfd = bfd_cfg.value["bfd"]
          # disable - (optional) is a type of number
          disable = bfd_cfg.value["disable"]
        }
      }

      dynamic "csnp_interval_list" {
        for_each = isis.value.csnp_interval_list
        content {
          # csnp_interval - (optional) is a type of number
          csnp_interval = csnp_interval_list.value["csnp_interval"]
          # level - (optional) is a type of string
          level = csnp_interval_list.value["level"]
        }
      }

      dynamic "hello_interval_list" {
        for_each = isis.value.hello_interval_list
        content {
          # hello_interval - (optional) is a type of number
          hello_interval = hello_interval_list.value["hello_interval"]
          # level - (optional) is a type of string
          level = hello_interval_list.value["level"]
        }
      }

      dynamic "hello_interval_minimal_list" {
        for_each = isis.value.hello_interval_minimal_list
        content {
          # hello_interval_minimal - (optional) is a type of number
          hello_interval_minimal = hello_interval_minimal_list.value["hello_interval_minimal"]
          # level - (optional) is a type of string
          level = hello_interval_minimal_list.value["level"]
        }
      }

      dynamic "hello_multiplier_list" {
        for_each = isis.value.hello_multiplier_list
        content {
          # hello_multiplier - (optional) is a type of number
          hello_multiplier = hello_multiplier_list.value["hello_multiplier"]
          # level - (optional) is a type of string
          level = hello_multiplier_list.value["level"]
        }
      }

      dynamic "mesh_group" {
        for_each = isis.value.mesh_group
        content {
          # blocked - (optional) is a type of number
          blocked = mesh_group.value["blocked"]
          # value - (optional) is a type of number
          value = mesh_group.value["value"]
        }
      }

      dynamic "metric_list" {
        for_each = isis.value.metric_list
        content {
          # level - (optional) is a type of string
          level = metric_list.value["level"]
          # metric - (optional) is a type of number
          metric = metric_list.value["metric"]
        }
      }

      dynamic "password_list" {
        for_each = isis.value.password_list
        content {
          # level - (optional) is a type of string
          level = password_list.value["level"]
          # password - (optional) is a type of string
          password = password_list.value["password"]
        }
      }

      dynamic "priority_list" {
        for_each = isis.value.priority_list
        content {
          # level - (optional) is a type of string
          level = priority_list.value["level"]
          # priority - (optional) is a type of number
          priority = priority_list.value["priority"]
        }
      }

      dynamic "wide_metric_list" {
        for_each = isis.value.wide_metric_list
        content {
          # level - (optional) is a type of string
          level = wide_metric_list.value["level"]
          # wide_metric - (optional) is a type of number
          wide_metric = wide_metric_list.value["wide_metric"]
        }
      }

    }
  }

  dynamic "lw_4o6" {
    for_each = var.lw_4o6
    content {
      # inside - (optional) is a type of number
      inside = lw_4o6.value["inside"]
      # outside - (optional) is a type of number
      outside = lw_4o6.value["outside"]
      # uuid - (optional) is a type of string
      uuid = lw_4o6.value["uuid"]
    }
  }

  dynamic "map" {
    for_each = var.map
    content {
      # inside - (optional) is a type of number
      inside = map.value["inside"]
      # map_t_inside - (optional) is a type of number
      map_t_inside = map.value["map_t_inside"]
      # map_t_outside - (optional) is a type of number
      map_t_outside = map.value["map_t_outside"]
      # outside - (optional) is a type of number
      outside = map.value["outside"]
      # uuid - (optional) is a type of string
      uuid = map.value["uuid"]
    }
  }

  dynamic "nptv6" {
    for_each = var.nptv6
    content {

      dynamic "domain_list" {
        for_each = nptv6.value.domain_list
        content {
          # bind_type - (optional) is a type of string
          bind_type = domain_list.value["bind_type"]
          # domain_name - (optional) is a type of string
          domain_name = domain_list.value["domain_name"]
          # uuid - (optional) is a type of string
          uuid = domain_list.value["uuid"]
        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      # counters1 - (optional) is a type of string
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_ve.this.id
}

output "this" {
  value = thunder_interface_ve.this
}
```

[top](#index)