# fortios_system_sdwan

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
module "fortios_system_sdwan" {
  source = "./modules/fortios/r/fortios_system_sdwan"

  # duplication_max_num - (optional) is a type of number
  duplication_max_num = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fail_detect - (optional) is a type of string
  fail_detect = null
  # load_balance_mode - (optional) is a type of string
  load_balance_mode = null
  # neighbor_hold_boot_time - (optional) is a type of number
  neighbor_hold_boot_time = null
  # neighbor_hold_down - (optional) is a type of string
  neighbor_hold_down = null
  # neighbor_hold_down_time - (optional) is a type of number
  neighbor_hold_down_time = null
  # status - (optional) is a type of string
  status = null

  duplication = [{
    dstaddr = [{
      name = null
    }]
    dstaddr6 = [{
      name = null
    }]
    dstintf = [{
      name = null
    }]
    id                    = null
    packet_de_duplication = null
    packet_duplication    = null
    service = [{
      name = null
    }]
    service_id = [{
      id = null
    }]
    srcaddr = [{
      name = null
    }]
    srcaddr6 = [{
      name = null
    }]
    srcintf = [{
      name = null
    }]
  }]

  fail_alert_interfaces = [{
    name = null
  }]

  health_check = [{
    addr_mode          = null
    diffservcode       = null
    dns_match_ip       = null
    dns_request_domain = null
    failtime           = null
    ftp_file           = null
    ftp_mode           = null
    ha_priority        = null
    http_agent         = null
    http_get           = null
    http_match         = null
    interval           = null
    members = [{
      seq_num = null
    }]
    name                    = null
    packet_size             = null
    password                = null
    port                    = null
    probe_count             = null
    probe_packets           = null
    probe_timeout           = null
    protocol                = null
    quality_measured_method = null
    recoverytime            = null
    security_mode           = null
    server                  = null
    sla = [{
      id                   = null
      jitter_threshold     = null
      latency_threshold    = null
      link_cost_factor     = null
      packetloss_threshold = null
    }]
    sla_fail_log_period          = null
    sla_pass_log_period          = null
    system_dns                   = null
    threshold_alert_jitter       = null
    threshold_alert_latency      = null
    threshold_alert_packetloss   = null
    threshold_warning_jitter     = null
    threshold_warning_latency    = null
    threshold_warning_packetloss = null
    update_cascade_interface     = null
    update_static_route          = null
    user                         = null
  }]

  members = [{
    comment                     = null
    cost                        = null
    gateway                     = null
    gateway6                    = null
    ingress_spillover_threshold = null
    interface                   = null
    priority                    = null
    priority6                   = null
    seq_num                     = null
    source                      = null
    source6                     = null
    spillover_threshold         = null
    status                      = null
    volume_ratio                = null
    weight                      = null
    zone                        = null
  }]

  neighbor = [{
    health_check = null
    ip           = null
    member       = null
    role         = null
    sla_id       = null
  }]

  service = [{
    addr_mode        = null
    bandwidth_weight = null
    default          = null
    dscp_forward     = null
    dscp_forward_tag = null
    dscp_reverse     = null
    dscp_reverse_tag = null
    dst = [{
      name = null
    }]
    dst6 = [{
      name = null
    }]
    dst_negate = null
    end_port   = null
    gateway    = null
    groups = [{
      name = null
    }]
    hash_mode = null
    health_check = [{
      name = null
    }]
    hold_down_time = null
    id             = null
    input_device = [{
      name = null
    }]
    input_device_negate = null
    internet_service    = null
    internet_service_app_ctrl = [{
      id = null
    }]
    internet_service_app_ctrl_group = [{
      name = null
    }]
    internet_service_custom = [{
      name = null
    }]
    internet_service_custom_group = [{
      name = null
    }]
    internet_service_group = [{
      name = null
    }]
    internet_service_name = [{
      name = null
    }]
    jitter_weight            = null
    latency_weight           = null
    link_cost_factor         = null
    link_cost_threshold      = null
    minimum_sla_meet_members = null
    mode                     = null
    name                     = null
    packet_loss_weight       = null
    priority_members = [{
      seq_num = null
    }]
    protocol     = null
    quality_link = null
    role         = null
    route_tag    = null
    sla = [{
      health_check = null
      id           = null
    }]
    sla_compare_method = null
    src = [{
      name = null
    }]
    src6 = [{
      name = null
    }]
    src_negate        = null
    standalone_action = null
    start_port        = null
    status            = null
    tie_break         = null
    tos               = null
    tos_mask          = null
    use_shortcut_sla  = null
    users = [{
      name = null
    }]
  }]

  zone = [{
    name                  = null
    service_sla_tie_break = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "duplication_max_num" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fail_detect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balance_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "neighbor_hold_boot_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "neighbor_hold_down" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "neighbor_hold_down_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "duplication" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dstaddr = list(object(
        {
          name = string
        }
      ))
      dstaddr6 = list(object(
        {
          name = string
        }
      ))
      dstintf = list(object(
        {
          name = string
        }
      ))
      id                    = number
      packet_de_duplication = string
      packet_duplication    = string
      service = list(object(
        {
          name = string
        }
      ))
      service_id = list(object(
        {
          id = number
        }
      ))
      srcaddr = list(object(
        {
          name = string
        }
      ))
      srcaddr6 = list(object(
        {
          name = string
        }
      ))
      srcintf = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "fail_alert_interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "health_check" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr_mode          = string
      diffservcode       = string
      dns_match_ip       = string
      dns_request_domain = string
      failtime           = number
      ftp_file           = string
      ftp_mode           = string
      ha_priority        = number
      http_agent         = string
      http_get           = string
      http_match         = string
      interval           = number
      members = list(object(
        {
          seq_num = number
        }
      ))
      name                    = string
      packet_size             = number
      password                = string
      port                    = number
      probe_count             = number
      probe_packets           = string
      probe_timeout           = number
      protocol                = string
      quality_measured_method = string
      recoverytime            = number
      security_mode           = string
      server                  = string
      sla = list(object(
        {
          id                   = number
          jitter_threshold     = number
          latency_threshold    = number
          link_cost_factor     = string
          packetloss_threshold = number
        }
      ))
      sla_fail_log_period          = number
      sla_pass_log_period          = number
      system_dns                   = string
      threshold_alert_jitter       = number
      threshold_alert_latency      = number
      threshold_alert_packetloss   = number
      threshold_warning_jitter     = number
      threshold_warning_latency    = number
      threshold_warning_packetloss = number
      update_cascade_interface     = string
      update_static_route          = string
      user                         = string
    }
  ))
  default = []
}

variable "members" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment                     = string
      cost                        = number
      gateway                     = string
      gateway6                    = string
      ingress_spillover_threshold = number
      interface                   = string
      priority                    = number
      priority6                   = number
      seq_num                     = number
      source                      = string
      source6                     = string
      spillover_threshold         = number
      status                      = string
      volume_ratio                = number
      weight                      = number
      zone                        = string
    }
  ))
  default = []
}

variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      health_check = string
      ip           = string
      member       = number
      role         = string
      sla_id       = number
    }
  ))
  default = []
}

variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr_mode        = string
      bandwidth_weight = number
      default          = string
      dscp_forward     = string
      dscp_forward_tag = string
      dscp_reverse     = string
      dscp_reverse_tag = string
      dst = list(object(
        {
          name = string
        }
      ))
      dst6 = list(object(
        {
          name = string
        }
      ))
      dst_negate = string
      end_port   = number
      gateway    = string
      groups = list(object(
        {
          name = string
        }
      ))
      hash_mode = string
      health_check = list(object(
        {
          name = string
        }
      ))
      hold_down_time = number
      id             = number
      input_device = list(object(
        {
          name = string
        }
      ))
      input_device_negate = string
      internet_service    = string
      internet_service_app_ctrl = list(object(
        {
          id = number
        }
      ))
      internet_service_app_ctrl_group = list(object(
        {
          name = string
        }
      ))
      internet_service_custom = list(object(
        {
          name = string
        }
      ))
      internet_service_custom_group = list(object(
        {
          name = string
        }
      ))
      internet_service_group = list(object(
        {
          name = string
        }
      ))
      internet_service_name = list(object(
        {
          name = string
        }
      ))
      jitter_weight            = number
      latency_weight           = number
      link_cost_factor         = string
      link_cost_threshold      = number
      minimum_sla_meet_members = number
      mode                     = string
      name                     = string
      packet_loss_weight       = number
      priority_members = list(object(
        {
          seq_num = number
        }
      ))
      protocol     = number
      quality_link = number
      role         = string
      route_tag    = number
      sla = list(object(
        {
          health_check = string
          id           = number
        }
      ))
      sla_compare_method = string
      src = list(object(
        {
          name = string
        }
      ))
      src6 = list(object(
        {
          name = string
        }
      ))
      src_negate        = string
      standalone_action = string
      start_port        = number
      status            = string
      tie_break         = string
      tos               = string
      tos_mask          = string
      use_shortcut_sla  = string
      users = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "zone" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name                  = string
      service_sla_tie_break = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_sdwan" "this" {
  # duplication_max_num - (optional) is a type of number
  duplication_max_num = var.duplication_max_num
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fail_detect - (optional) is a type of string
  fail_detect = var.fail_detect
  # load_balance_mode - (optional) is a type of string
  load_balance_mode = var.load_balance_mode
  # neighbor_hold_boot_time - (optional) is a type of number
  neighbor_hold_boot_time = var.neighbor_hold_boot_time
  # neighbor_hold_down - (optional) is a type of string
  neighbor_hold_down = var.neighbor_hold_down
  # neighbor_hold_down_time - (optional) is a type of number
  neighbor_hold_down_time = var.neighbor_hold_down_time
  # status - (optional) is a type of string
  status = var.status

  dynamic "duplication" {
    for_each = var.duplication
    content {
      # id - (optional) is a type of number
      id = duplication.value["id"]
      # packet_de_duplication - (optional) is a type of string
      packet_de_duplication = duplication.value["packet_de_duplication"]
      # packet_duplication - (optional) is a type of string
      packet_duplication = duplication.value["packet_duplication"]

      dynamic "dstaddr" {
        for_each = duplication.value.dstaddr
        content {
          # name - (optional) is a type of string
          name = dstaddr.value["name"]
        }
      }

      dynamic "dstaddr6" {
        for_each = duplication.value.dstaddr6
        content {
          # name - (optional) is a type of string
          name = dstaddr6.value["name"]
        }
      }

      dynamic "dstintf" {
        for_each = duplication.value.dstintf
        content {
          # name - (optional) is a type of string
          name = dstintf.value["name"]
        }
      }

      dynamic "service" {
        for_each = duplication.value.service
        content {
          # name - (optional) is a type of string
          name = service.value["name"]
        }
      }

      dynamic "service_id" {
        for_each = duplication.value.service_id
        content {
          # id - (optional) is a type of number
          id = service_id.value["id"]
        }
      }

      dynamic "srcaddr" {
        for_each = duplication.value.srcaddr
        content {
          # name - (optional) is a type of string
          name = srcaddr.value["name"]
        }
      }

      dynamic "srcaddr6" {
        for_each = duplication.value.srcaddr6
        content {
          # name - (optional) is a type of string
          name = srcaddr6.value["name"]
        }
      }

      dynamic "srcintf" {
        for_each = duplication.value.srcintf
        content {
          # name - (optional) is a type of string
          name = srcintf.value["name"]
        }
      }

    }
  }

  dynamic "fail_alert_interfaces" {
    for_each = var.fail_alert_interfaces
    content {
      # name - (optional) is a type of string
      name = fail_alert_interfaces.value["name"]
    }
  }

  dynamic "health_check" {
    for_each = var.health_check
    content {
      # addr_mode - (optional) is a type of string
      addr_mode = health_check.value["addr_mode"]
      # diffservcode - (optional) is a type of string
      diffservcode = health_check.value["diffservcode"]
      # dns_match_ip - (optional) is a type of string
      dns_match_ip = health_check.value["dns_match_ip"]
      # dns_request_domain - (optional) is a type of string
      dns_request_domain = health_check.value["dns_request_domain"]
      # failtime - (optional) is a type of number
      failtime = health_check.value["failtime"]
      # ftp_file - (optional) is a type of string
      ftp_file = health_check.value["ftp_file"]
      # ftp_mode - (optional) is a type of string
      ftp_mode = health_check.value["ftp_mode"]
      # ha_priority - (optional) is a type of number
      ha_priority = health_check.value["ha_priority"]
      # http_agent - (optional) is a type of string
      http_agent = health_check.value["http_agent"]
      # http_get - (optional) is a type of string
      http_get = health_check.value["http_get"]
      # http_match - (optional) is a type of string
      http_match = health_check.value["http_match"]
      # interval - (optional) is a type of number
      interval = health_check.value["interval"]
      # name - (optional) is a type of string
      name = health_check.value["name"]
      # packet_size - (optional) is a type of number
      packet_size = health_check.value["packet_size"]
      # password - (optional) is a type of string
      password = health_check.value["password"]
      # port - (optional) is a type of number
      port = health_check.value["port"]
      # probe_count - (optional) is a type of number
      probe_count = health_check.value["probe_count"]
      # probe_packets - (optional) is a type of string
      probe_packets = health_check.value["probe_packets"]
      # probe_timeout - (optional) is a type of number
      probe_timeout = health_check.value["probe_timeout"]
      # protocol - (optional) is a type of string
      protocol = health_check.value["protocol"]
      # quality_measured_method - (optional) is a type of string
      quality_measured_method = health_check.value["quality_measured_method"]
      # recoverytime - (optional) is a type of number
      recoverytime = health_check.value["recoverytime"]
      # security_mode - (optional) is a type of string
      security_mode = health_check.value["security_mode"]
      # server - (optional) is a type of string
      server = health_check.value["server"]
      # sla_fail_log_period - (optional) is a type of number
      sla_fail_log_period = health_check.value["sla_fail_log_period"]
      # sla_pass_log_period - (optional) is a type of number
      sla_pass_log_period = health_check.value["sla_pass_log_period"]
      # system_dns - (optional) is a type of string
      system_dns = health_check.value["system_dns"]
      # threshold_alert_jitter - (optional) is a type of number
      threshold_alert_jitter = health_check.value["threshold_alert_jitter"]
      # threshold_alert_latency - (optional) is a type of number
      threshold_alert_latency = health_check.value["threshold_alert_latency"]
      # threshold_alert_packetloss - (optional) is a type of number
      threshold_alert_packetloss = health_check.value["threshold_alert_packetloss"]
      # threshold_warning_jitter - (optional) is a type of number
      threshold_warning_jitter = health_check.value["threshold_warning_jitter"]
      # threshold_warning_latency - (optional) is a type of number
      threshold_warning_latency = health_check.value["threshold_warning_latency"]
      # threshold_warning_packetloss - (optional) is a type of number
      threshold_warning_packetloss = health_check.value["threshold_warning_packetloss"]
      # update_cascade_interface - (optional) is a type of string
      update_cascade_interface = health_check.value["update_cascade_interface"]
      # update_static_route - (optional) is a type of string
      update_static_route = health_check.value["update_static_route"]
      # user - (optional) is a type of string
      user = health_check.value["user"]

      dynamic "members" {
        for_each = health_check.value.members
        content {
          # seq_num - (optional) is a type of number
          seq_num = members.value["seq_num"]
        }
      }

      dynamic "sla" {
        for_each = health_check.value.sla
        content {
          # id - (optional) is a type of number
          id = sla.value["id"]
          # jitter_threshold - (optional) is a type of number
          jitter_threshold = sla.value["jitter_threshold"]
          # latency_threshold - (optional) is a type of number
          latency_threshold = sla.value["latency_threshold"]
          # link_cost_factor - (optional) is a type of string
          link_cost_factor = sla.value["link_cost_factor"]
          # packetloss_threshold - (optional) is a type of number
          packetloss_threshold = sla.value["packetloss_threshold"]
        }
      }

    }
  }

  dynamic "members" {
    for_each = var.members
    content {
      # comment - (optional) is a type of string
      comment = members.value["comment"]
      # cost - (optional) is a type of number
      cost = members.value["cost"]
      # gateway - (optional) is a type of string
      gateway = members.value["gateway"]
      # gateway6 - (optional) is a type of string
      gateway6 = members.value["gateway6"]
      # ingress_spillover_threshold - (optional) is a type of number
      ingress_spillover_threshold = members.value["ingress_spillover_threshold"]
      # interface - (optional) is a type of string
      interface = members.value["interface"]
      # priority - (optional) is a type of number
      priority = members.value["priority"]
      # priority6 - (optional) is a type of number
      priority6 = members.value["priority6"]
      # seq_num - (optional) is a type of number
      seq_num = members.value["seq_num"]
      # source - (optional) is a type of string
      source = members.value["source"]
      # source6 - (optional) is a type of string
      source6 = members.value["source6"]
      # spillover_threshold - (optional) is a type of number
      spillover_threshold = members.value["spillover_threshold"]
      # status - (optional) is a type of string
      status = members.value["status"]
      # volume_ratio - (optional) is a type of number
      volume_ratio = members.value["volume_ratio"]
      # weight - (optional) is a type of number
      weight = members.value["weight"]
      # zone - (optional) is a type of string
      zone = members.value["zone"]
    }
  }

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      # health_check - (optional) is a type of string
      health_check = neighbor.value["health_check"]
      # ip - (optional) is a type of string
      ip = neighbor.value["ip"]
      # member - (optional) is a type of number
      member = neighbor.value["member"]
      # role - (optional) is a type of string
      role = neighbor.value["role"]
      # sla_id - (optional) is a type of number
      sla_id = neighbor.value["sla_id"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      # addr_mode - (optional) is a type of string
      addr_mode = service.value["addr_mode"]
      # bandwidth_weight - (optional) is a type of number
      bandwidth_weight = service.value["bandwidth_weight"]
      # default - (optional) is a type of string
      default = service.value["default"]
      # dscp_forward - (optional) is a type of string
      dscp_forward = service.value["dscp_forward"]
      # dscp_forward_tag - (optional) is a type of string
      dscp_forward_tag = service.value["dscp_forward_tag"]
      # dscp_reverse - (optional) is a type of string
      dscp_reverse = service.value["dscp_reverse"]
      # dscp_reverse_tag - (optional) is a type of string
      dscp_reverse_tag = service.value["dscp_reverse_tag"]
      # dst_negate - (optional) is a type of string
      dst_negate = service.value["dst_negate"]
      # end_port - (optional) is a type of number
      end_port = service.value["end_port"]
      # gateway - (optional) is a type of string
      gateway = service.value["gateway"]
      # hash_mode - (optional) is a type of string
      hash_mode = service.value["hash_mode"]
      # hold_down_time - (optional) is a type of number
      hold_down_time = service.value["hold_down_time"]
      # id - (optional) is a type of number
      id = service.value["id"]
      # input_device_negate - (optional) is a type of string
      input_device_negate = service.value["input_device_negate"]
      # internet_service - (optional) is a type of string
      internet_service = service.value["internet_service"]
      # jitter_weight - (optional) is a type of number
      jitter_weight = service.value["jitter_weight"]
      # latency_weight - (optional) is a type of number
      latency_weight = service.value["latency_weight"]
      # link_cost_factor - (optional) is a type of string
      link_cost_factor = service.value["link_cost_factor"]
      # link_cost_threshold - (optional) is a type of number
      link_cost_threshold = service.value["link_cost_threshold"]
      # minimum_sla_meet_members - (optional) is a type of number
      minimum_sla_meet_members = service.value["minimum_sla_meet_members"]
      # mode - (optional) is a type of string
      mode = service.value["mode"]
      # name - (optional) is a type of string
      name = service.value["name"]
      # packet_loss_weight - (optional) is a type of number
      packet_loss_weight = service.value["packet_loss_weight"]
      # protocol - (optional) is a type of number
      protocol = service.value["protocol"]
      # quality_link - (optional) is a type of number
      quality_link = service.value["quality_link"]
      # role - (optional) is a type of string
      role = service.value["role"]
      # route_tag - (optional) is a type of number
      route_tag = service.value["route_tag"]
      # sla_compare_method - (optional) is a type of string
      sla_compare_method = service.value["sla_compare_method"]
      # src_negate - (optional) is a type of string
      src_negate = service.value["src_negate"]
      # standalone_action - (optional) is a type of string
      standalone_action = service.value["standalone_action"]
      # start_port - (optional) is a type of number
      start_port = service.value["start_port"]
      # status - (optional) is a type of string
      status = service.value["status"]
      # tie_break - (optional) is a type of string
      tie_break = service.value["tie_break"]
      # tos - (optional) is a type of string
      tos = service.value["tos"]
      # tos_mask - (optional) is a type of string
      tos_mask = service.value["tos_mask"]
      # use_shortcut_sla - (optional) is a type of string
      use_shortcut_sla = service.value["use_shortcut_sla"]

      dynamic "dst" {
        for_each = service.value.dst
        content {
          # name - (optional) is a type of string
          name = dst.value["name"]
        }
      }

      dynamic "dst6" {
        for_each = service.value.dst6
        content {
          # name - (optional) is a type of string
          name = dst6.value["name"]
        }
      }

      dynamic "groups" {
        for_each = service.value.groups
        content {
          # name - (optional) is a type of string
          name = groups.value["name"]
        }
      }

      dynamic "health_check" {
        for_each = service.value.health_check
        content {
          # name - (optional) is a type of string
          name = health_check.value["name"]
        }
      }

      dynamic "input_device" {
        for_each = service.value.input_device
        content {
          # name - (optional) is a type of string
          name = input_device.value["name"]
        }
      }

      dynamic "internet_service_app_ctrl" {
        for_each = service.value.internet_service_app_ctrl
        content {
          # id - (optional) is a type of number
          id = internet_service_app_ctrl.value["id"]
        }
      }

      dynamic "internet_service_app_ctrl_group" {
        for_each = service.value.internet_service_app_ctrl_group
        content {
          # name - (optional) is a type of string
          name = internet_service_app_ctrl_group.value["name"]
        }
      }

      dynamic "internet_service_custom" {
        for_each = service.value.internet_service_custom
        content {
          # name - (optional) is a type of string
          name = internet_service_custom.value["name"]
        }
      }

      dynamic "internet_service_custom_group" {
        for_each = service.value.internet_service_custom_group
        content {
          # name - (optional) is a type of string
          name = internet_service_custom_group.value["name"]
        }
      }

      dynamic "internet_service_group" {
        for_each = service.value.internet_service_group
        content {
          # name - (optional) is a type of string
          name = internet_service_group.value["name"]
        }
      }

      dynamic "internet_service_name" {
        for_each = service.value.internet_service_name
        content {
          # name - (optional) is a type of string
          name = internet_service_name.value["name"]
        }
      }

      dynamic "priority_members" {
        for_each = service.value.priority_members
        content {
          # seq_num - (optional) is a type of number
          seq_num = priority_members.value["seq_num"]
        }
      }

      dynamic "sla" {
        for_each = service.value.sla
        content {
          # health_check - (optional) is a type of string
          health_check = sla.value["health_check"]
          # id - (optional) is a type of number
          id = sla.value["id"]
        }
      }

      dynamic "src" {
        for_each = service.value.src
        content {
          # name - (optional) is a type of string
          name = src.value["name"]
        }
      }

      dynamic "src6" {
        for_each = service.value.src6
        content {
          # name - (optional) is a type of string
          name = src6.value["name"]
        }
      }

      dynamic "users" {
        for_each = service.value.users
        content {
          # name - (optional) is a type of string
          name = users.value["name"]
        }
      }

    }
  }

  dynamic "zone" {
    for_each = var.zone
    content {
      # name - (optional) is a type of string
      name = zone.value["name"]
      # service_sla_tie_break - (optional) is a type of string
      service_sla_tie_break = zone.value["service_sla_tie_break"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "duplication_max_num" {
  description = "returns a number"
  value       = fortios_system_sdwan.this.duplication_max_num
}

output "fail_detect" {
  description = "returns a string"
  value       = fortios_system_sdwan.this.fail_detect
}

output "id" {
  description = "returns a string"
  value       = fortios_system_sdwan.this.id
}

output "load_balance_mode" {
  description = "returns a string"
  value       = fortios_system_sdwan.this.load_balance_mode
}

output "neighbor_hold_boot_time" {
  description = "returns a number"
  value       = fortios_system_sdwan.this.neighbor_hold_boot_time
}

output "neighbor_hold_down" {
  description = "returns a string"
  value       = fortios_system_sdwan.this.neighbor_hold_down
}

output "neighbor_hold_down_time" {
  description = "returns a number"
  value       = fortios_system_sdwan.this.neighbor_hold_down_time
}

output "status" {
  description = "returns a string"
  value       = fortios_system_sdwan.this.status
}

output "this" {
  value = fortios_system_sdwan.this
}
```

[top](#index)