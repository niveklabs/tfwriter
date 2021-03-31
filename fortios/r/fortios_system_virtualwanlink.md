# fortios_system_virtualwanlink

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
module "fortios_system_virtualwanlink" {
  source = "./modules/fortios/r/fortios_system_virtualwanlink"

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

  fail_alert_interfaces = [{
    name = null
  }]

  health_check = [{
    addr_mode          = null
    diffservcode       = null
    dns_request_domain = null
    failtime           = null
    ha_priority        = null
    http_agent         = null
    http_get           = null
    http_match         = null
    interval           = null
    members = [{
      seq_num = null
    }]
    name          = null
    packet_size   = null
    password      = null
    port          = null
    probe_count   = null
    probe_packets = null
    probe_timeout = null
    protocol      = null
    recoverytime  = null
    security_mode = null
    server        = null
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
  }]

  members = [{
    comment                     = null
    cost                        = null
    gateway                     = null
    gateway6                    = null
    ingress_spillover_threshold = null
    interface                   = null
    priority                    = null
    seq_num                     = null
    source                      = null
    source6                     = null
    spillover_threshold         = null
    status                      = null
    volume_ratio                = null
    weight                      = null
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
    health_check   = null
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
    internet_service_ctrl = [{
      id = null
    }]
    internet_service_ctrl_group = [{
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
    internet_service_id = [{
      id = null
    }]
    internet_service_name = [{
      name = null
    }]
    jitter_weight       = null
    latency_weight      = null
    link_cost_factor    = null
    link_cost_threshold = null
    member              = null
    mode                = null
    name                = null
    packet_loss_weight  = null
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
    tos               = null
    tos_mask          = null
    users = [{
      name = null
    }]
  }]

  zone = [{
    name = null
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
      dns_request_domain = string
      failtime           = number
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
      name          = string
      packet_size   = number
      password      = string
      port          = number
      probe_count   = number
      probe_packets = string
      probe_timeout = number
      protocol      = string
      recoverytime  = number
      security_mode = string
      server        = string
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
      seq_num                     = number
      source                      = string
      source6                     = string
      spillover_threshold         = number
      status                      = string
      volume_ratio                = number
      weight                      = number
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
      health_check   = string
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
      internet_service_ctrl = list(object(
        {
          id = number
        }
      ))
      internet_service_ctrl_group = list(object(
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
      internet_service_id = list(object(
        {
          id = number
        }
      ))
      internet_service_name = list(object(
        {
          name = string
        }
      ))
      jitter_weight       = number
      latency_weight      = number
      link_cost_factor    = string
      link_cost_threshold = number
      member              = number
      mode                = string
      name                = string
      packet_loss_weight  = number
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
      tos               = string
      tos_mask          = string
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
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_virtualwanlink" "this" {
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  fail_detect             = var.fail_detect
  load_balance_mode       = var.load_balance_mode
  neighbor_hold_boot_time = var.neighbor_hold_boot_time
  neighbor_hold_down      = var.neighbor_hold_down
  neighbor_hold_down_time = var.neighbor_hold_down_time
  status                  = var.status

  dynamic "fail_alert_interfaces" {
    for_each = var.fail_alert_interfaces
    content {
      name = fail_alert_interfaces.value["name"]
    }
  }

  dynamic "health_check" {
    for_each = var.health_check
    content {
      addr_mode                    = health_check.value["addr_mode"]
      diffservcode                 = health_check.value["diffservcode"]
      dns_request_domain           = health_check.value["dns_request_domain"]
      failtime                     = health_check.value["failtime"]
      ha_priority                  = health_check.value["ha_priority"]
      http_agent                   = health_check.value["http_agent"]
      http_get                     = health_check.value["http_get"]
      http_match                   = health_check.value["http_match"]
      interval                     = health_check.value["interval"]
      name                         = health_check.value["name"]
      packet_size                  = health_check.value["packet_size"]
      password                     = health_check.value["password"]
      port                         = health_check.value["port"]
      probe_count                  = health_check.value["probe_count"]
      probe_packets                = health_check.value["probe_packets"]
      probe_timeout                = health_check.value["probe_timeout"]
      protocol                     = health_check.value["protocol"]
      recoverytime                 = health_check.value["recoverytime"]
      security_mode                = health_check.value["security_mode"]
      server                       = health_check.value["server"]
      sla_fail_log_period          = health_check.value["sla_fail_log_period"]
      sla_pass_log_period          = health_check.value["sla_pass_log_period"]
      system_dns                   = health_check.value["system_dns"]
      threshold_alert_jitter       = health_check.value["threshold_alert_jitter"]
      threshold_alert_latency      = health_check.value["threshold_alert_latency"]
      threshold_alert_packetloss   = health_check.value["threshold_alert_packetloss"]
      threshold_warning_jitter     = health_check.value["threshold_warning_jitter"]
      threshold_warning_latency    = health_check.value["threshold_warning_latency"]
      threshold_warning_packetloss = health_check.value["threshold_warning_packetloss"]
      update_cascade_interface     = health_check.value["update_cascade_interface"]
      update_static_route          = health_check.value["update_static_route"]

      dynamic "members" {
        for_each = health_check.value.members
        content {
          seq_num = members.value["seq_num"]
        }
      }

      dynamic "sla" {
        for_each = health_check.value.sla
        content {
          id                   = sla.value["id"]
          jitter_threshold     = sla.value["jitter_threshold"]
          latency_threshold    = sla.value["latency_threshold"]
          link_cost_factor     = sla.value["link_cost_factor"]
          packetloss_threshold = sla.value["packetloss_threshold"]
        }
      }

    }
  }

  dynamic "members" {
    for_each = var.members
    content {
      comment                     = members.value["comment"]
      cost                        = members.value["cost"]
      gateway                     = members.value["gateway"]
      gateway6                    = members.value["gateway6"]
      ingress_spillover_threshold = members.value["ingress_spillover_threshold"]
      interface                   = members.value["interface"]
      priority                    = members.value["priority"]
      seq_num                     = members.value["seq_num"]
      source                      = members.value["source"]
      source6                     = members.value["source6"]
      spillover_threshold         = members.value["spillover_threshold"]
      status                      = members.value["status"]
      volume_ratio                = members.value["volume_ratio"]
      weight                      = members.value["weight"]
    }
  }

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      health_check = neighbor.value["health_check"]
      ip           = neighbor.value["ip"]
      member       = neighbor.value["member"]
      role         = neighbor.value["role"]
      sla_id       = neighbor.value["sla_id"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      addr_mode           = service.value["addr_mode"]
      bandwidth_weight    = service.value["bandwidth_weight"]
      default             = service.value["default"]
      dscp_forward        = service.value["dscp_forward"]
      dscp_forward_tag    = service.value["dscp_forward_tag"]
      dscp_reverse        = service.value["dscp_reverse"]
      dscp_reverse_tag    = service.value["dscp_reverse_tag"]
      dst_negate          = service.value["dst_negate"]
      end_port            = service.value["end_port"]
      gateway             = service.value["gateway"]
      health_check        = service.value["health_check"]
      hold_down_time      = service.value["hold_down_time"]
      id                  = service.value["id"]
      input_device_negate = service.value["input_device_negate"]
      internet_service    = service.value["internet_service"]
      jitter_weight       = service.value["jitter_weight"]
      latency_weight      = service.value["latency_weight"]
      link_cost_factor    = service.value["link_cost_factor"]
      link_cost_threshold = service.value["link_cost_threshold"]
      member              = service.value["member"]
      mode                = service.value["mode"]
      name                = service.value["name"]
      packet_loss_weight  = service.value["packet_loss_weight"]
      protocol            = service.value["protocol"]
      quality_link        = service.value["quality_link"]
      role                = service.value["role"]
      route_tag           = service.value["route_tag"]
      sla_compare_method  = service.value["sla_compare_method"]
      src_negate          = service.value["src_negate"]
      standalone_action   = service.value["standalone_action"]
      start_port          = service.value["start_port"]
      status              = service.value["status"]
      tos                 = service.value["tos"]
      tos_mask            = service.value["tos_mask"]

      dynamic "dst" {
        for_each = service.value.dst
        content {
          name = dst.value["name"]
        }
      }

      dynamic "dst6" {
        for_each = service.value.dst6
        content {
          name = dst6.value["name"]
        }
      }

      dynamic "groups" {
        for_each = service.value.groups
        content {
          name = groups.value["name"]
        }
      }

      dynamic "input_device" {
        for_each = service.value.input_device
        content {
          name = input_device.value["name"]
        }
      }

      dynamic "internet_service_app_ctrl" {
        for_each = service.value.internet_service_app_ctrl
        content {
          id = internet_service_app_ctrl.value["id"]
        }
      }

      dynamic "internet_service_app_ctrl_group" {
        for_each = service.value.internet_service_app_ctrl_group
        content {
          name = internet_service_app_ctrl_group.value["name"]
        }
      }

      dynamic "internet_service_ctrl" {
        for_each = service.value.internet_service_ctrl
        content {
          id = internet_service_ctrl.value["id"]
        }
      }

      dynamic "internet_service_ctrl_group" {
        for_each = service.value.internet_service_ctrl_group
        content {
          name = internet_service_ctrl_group.value["name"]
        }
      }

      dynamic "internet_service_custom" {
        for_each = service.value.internet_service_custom
        content {
          name = internet_service_custom.value["name"]
        }
      }

      dynamic "internet_service_custom_group" {
        for_each = service.value.internet_service_custom_group
        content {
          name = internet_service_custom_group.value["name"]
        }
      }

      dynamic "internet_service_group" {
        for_each = service.value.internet_service_group
        content {
          name = internet_service_group.value["name"]
        }
      }

      dynamic "internet_service_id" {
        for_each = service.value.internet_service_id
        content {
          id = internet_service_id.value["id"]
        }
      }

      dynamic "internet_service_name" {
        for_each = service.value.internet_service_name
        content {
          name = internet_service_name.value["name"]
        }
      }

      dynamic "priority_members" {
        for_each = service.value.priority_members
        content {
          seq_num = priority_members.value["seq_num"]
        }
      }

      dynamic "sla" {
        for_each = service.value.sla
        content {
          health_check = sla.value["health_check"]
          id           = sla.value["id"]
        }
      }

      dynamic "src" {
        for_each = service.value.src
        content {
          name = src.value["name"]
        }
      }

      dynamic "src6" {
        for_each = service.value.src6
        content {
          name = src6.value["name"]
        }
      }

      dynamic "users" {
        for_each = service.value.users
        content {
          name = users.value["name"]
        }
      }

    }
  }

  dynamic "zone" {
    for_each = var.zone
    content {
      name = zone.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fail_detect" {
  description = "returns a string"
  value       = fortios_system_virtualwanlink.this.fail_detect
}

output "id" {
  description = "returns a string"
  value       = fortios_system_virtualwanlink.this.id
}

output "load_balance_mode" {
  description = "returns a string"
  value       = fortios_system_virtualwanlink.this.load_balance_mode
}

output "neighbor_hold_boot_time" {
  description = "returns a number"
  value       = fortios_system_virtualwanlink.this.neighbor_hold_boot_time
}

output "neighbor_hold_down" {
  description = "returns a string"
  value       = fortios_system_virtualwanlink.this.neighbor_hold_down
}

output "neighbor_hold_down_time" {
  description = "returns a number"
  value       = fortios_system_virtualwanlink.this.neighbor_hold_down_time
}

output "status" {
  description = "returns a string"
  value       = fortios_system_virtualwanlink.this.status
}

output "this" {
  value = fortios_system_virtualwanlink.this
}
```

[top](#index)