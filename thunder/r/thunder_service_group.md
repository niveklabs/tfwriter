# thunder_service_group

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
module "thunder_service_group" {
  source = "./modules/thunder/r/thunder_service_group"

  # backup_server_event_log - (optional) is a type of number
  backup_server_event_log = null
  # conn_rate - (optional) is a type of number
  conn_rate = null
  # conn_rate_duration - (optional) is a type of number
  conn_rate_duration = null
  # conn_rate_grace_period - (optional) is a type of number
  conn_rate_grace_period = null
  # conn_rate_log - (optional) is a type of number
  conn_rate_log = null
  # conn_rate_revert_duration - (optional) is a type of number
  conn_rate_revert_duration = null
  # conn_revert_rate - (optional) is a type of number
  conn_revert_rate = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_disable - (optional) is a type of number
  health_check_disable = null
  # l4_session_revert_duration - (optional) is a type of number
  l4_session_revert_duration = null
  # l4_session_usage - (optional) is a type of number
  l4_session_usage = null
  # l4_session_usage_duration - (optional) is a type of number
  l4_session_usage_duration = null
  # l4_session_usage_grace_period - (optional) is a type of number
  l4_session_usage_grace_period = null
  # l4_session_usage_log - (optional) is a type of number
  l4_session_usage_log = null
  # l4_session_usage_revert_rate - (optional) is a type of number
  l4_session_usage_revert_rate = null
  # lb_method - (optional) is a type of string
  lb_method = null
  # lc_method - (optional) is a type of string
  lc_method = null
  # min_active_member - (optional) is a type of number
  min_active_member = null
  # min_active_member_action - (optional) is a type of string
  min_active_member_action = null
  # name - (optional) is a type of string
  name = null
  # priority_affinity - (optional) is a type of number
  priority_affinity = null
  # protocol - (optional) is a type of string
  protocol = null
  # pseudo_round_robin - (optional) is a type of number
  pseudo_round_robin = null
  # report_delay - (optional) is a type of number
  report_delay = null
  # reset_on_server_selection_fail - (optional) is a type of number
  reset_on_server_selection_fail = null
  # reset_priority_affinity - (optional) is a type of number
  reset_priority_affinity = null
  # rpt_ext_server - (optional) is a type of number
  rpt_ext_server = null
  # sample_rsp_time - (optional) is a type of number
  sample_rsp_time = null
  # shared_partition_policy_template - (optional) is a type of number
  shared_partition_policy_template = null
  # shared_partition_svcgrp_health_check - (optional) is a type of number
  shared_partition_svcgrp_health_check = null
  # stateless_auto_switch - (optional) is a type of number
  stateless_auto_switch = null
  # stateless_lb_method - (optional) is a type of string
  stateless_lb_method = null
  # stateless_lb_method2 - (optional) is a type of string
  stateless_lb_method2 = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
  # strict_select - (optional) is a type of number
  strict_select = null
  # svcgrp_health_check_shared - (optional) is a type of string
  svcgrp_health_check_shared = null
  # template_policy - (optional) is a type of string
  template_policy = null
  # template_policy_shared - (optional) is a type of string
  template_policy_shared = null
  # template_port - (optional) is a type of string
  template_port = null
  # template_server - (optional) is a type of string
  template_server = null
  # top_fastest - (optional) is a type of number
  top_fastest = null
  # top_slowest - (optional) is a type of number
  top_slowest = null
  # traffic_replication_mirror - (optional) is a type of number
  traffic_replication_mirror = null
  # traffic_replication_mirror_da_repl - (optional) is a type of number
  traffic_replication_mirror_da_repl = null
  # traffic_replication_mirror_ip_repl - (optional) is a type of number
  traffic_replication_mirror_ip_repl = null
  # traffic_replication_mirror_sa_da_repl - (optional) is a type of number
  traffic_replication_mirror_sa_da_repl = null
  # traffic_replication_mirror_sa_repl - (optional) is a type of number
  traffic_replication_mirror_sa_repl = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  member_list = [{
    fqdn_name                 = null
    host                      = null
    member_priority           = null
    member_state              = null
    member_stats_data_disable = null
    member_template           = null
    name                      = null
    port                      = null
    resolve_as                = null
    sampling_enable = [{
      counters1 = null
    }]
    server_ipv6_addr = null
    user_tag         = null
    uuid             = null
  }]

  priorities = [{
    priority        = null
    priority_action = null
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backup_server_event_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_revert_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_revert_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_stats" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l4_session_revert_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l4_session_usage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l4_session_usage_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l4_session_usage_grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l4_session_usage_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l4_session_usage_revert_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lb_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lc_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_active_member" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_active_member_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority_affinity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pseudo_round_robin" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "report_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_on_server_selection_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_priority_affinity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rpt_ext_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sample_rsp_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_policy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_svcgrp_health_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stateless_auto_switch" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stateless_lb_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stateless_lb_method2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stats_data_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_select" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "svcgrp_health_check_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_policy_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "top_fastest" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "top_slowest" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_replication_mirror" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_replication_mirror_da_repl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_replication_mirror_ip_repl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_replication_mirror_sa_da_repl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "traffic_replication_mirror_sa_repl" {
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

variable "member_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      fqdn_name                 = string
      host                      = string
      member_priority           = number
      member_state              = string
      member_stats_data_disable = number
      member_template           = string
      name                      = string
      port                      = number
      resolve_as                = string
      sampling_enable = list(object(
        {
          counters1 = string
        }
      ))
      server_ipv6_addr = string
      user_tag         = string
      uuid             = string
    }
  ))
  default = []
}

variable "priorities" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      priority        = number
      priority_action = string
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
resource "thunder_service_group" "this" {
  # backup_server_event_log - (optional) is a type of number
  backup_server_event_log = var.backup_server_event_log
  # conn_rate - (optional) is a type of number
  conn_rate = var.conn_rate
  # conn_rate_duration - (optional) is a type of number
  conn_rate_duration = var.conn_rate_duration
  # conn_rate_grace_period - (optional) is a type of number
  conn_rate_grace_period = var.conn_rate_grace_period
  # conn_rate_log - (optional) is a type of number
  conn_rate_log = var.conn_rate_log
  # conn_rate_revert_duration - (optional) is a type of number
  conn_rate_revert_duration = var.conn_rate_revert_duration
  # conn_revert_rate - (optional) is a type of number
  conn_revert_rate = var.conn_revert_rate
  # extended_stats - (optional) is a type of number
  extended_stats = var.extended_stats
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # health_check_disable - (optional) is a type of number
  health_check_disable = var.health_check_disable
  # l4_session_revert_duration - (optional) is a type of number
  l4_session_revert_duration = var.l4_session_revert_duration
  # l4_session_usage - (optional) is a type of number
  l4_session_usage = var.l4_session_usage
  # l4_session_usage_duration - (optional) is a type of number
  l4_session_usage_duration = var.l4_session_usage_duration
  # l4_session_usage_grace_period - (optional) is a type of number
  l4_session_usage_grace_period = var.l4_session_usage_grace_period
  # l4_session_usage_log - (optional) is a type of number
  l4_session_usage_log = var.l4_session_usage_log
  # l4_session_usage_revert_rate - (optional) is a type of number
  l4_session_usage_revert_rate = var.l4_session_usage_revert_rate
  # lb_method - (optional) is a type of string
  lb_method = var.lb_method
  # lc_method - (optional) is a type of string
  lc_method = var.lc_method
  # min_active_member - (optional) is a type of number
  min_active_member = var.min_active_member
  # min_active_member_action - (optional) is a type of string
  min_active_member_action = var.min_active_member_action
  # name - (optional) is a type of string
  name = var.name
  # priority_affinity - (optional) is a type of number
  priority_affinity = var.priority_affinity
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # pseudo_round_robin - (optional) is a type of number
  pseudo_round_robin = var.pseudo_round_robin
  # report_delay - (optional) is a type of number
  report_delay = var.report_delay
  # reset_on_server_selection_fail - (optional) is a type of number
  reset_on_server_selection_fail = var.reset_on_server_selection_fail
  # reset_priority_affinity - (optional) is a type of number
  reset_priority_affinity = var.reset_priority_affinity
  # rpt_ext_server - (optional) is a type of number
  rpt_ext_server = var.rpt_ext_server
  # sample_rsp_time - (optional) is a type of number
  sample_rsp_time = var.sample_rsp_time
  # shared_partition_policy_template - (optional) is a type of number
  shared_partition_policy_template = var.shared_partition_policy_template
  # shared_partition_svcgrp_health_check - (optional) is a type of number
  shared_partition_svcgrp_health_check = var.shared_partition_svcgrp_health_check
  # stateless_auto_switch - (optional) is a type of number
  stateless_auto_switch = var.stateless_auto_switch
  # stateless_lb_method - (optional) is a type of string
  stateless_lb_method = var.stateless_lb_method
  # stateless_lb_method2 - (optional) is a type of string
  stateless_lb_method2 = var.stateless_lb_method2
  # stats_data_action - (optional) is a type of string
  stats_data_action = var.stats_data_action
  # strict_select - (optional) is a type of number
  strict_select = var.strict_select
  # svcgrp_health_check_shared - (optional) is a type of string
  svcgrp_health_check_shared = var.svcgrp_health_check_shared
  # template_policy - (optional) is a type of string
  template_policy = var.template_policy
  # template_policy_shared - (optional) is a type of string
  template_policy_shared = var.template_policy_shared
  # template_port - (optional) is a type of string
  template_port = var.template_port
  # template_server - (optional) is a type of string
  template_server = var.template_server
  # top_fastest - (optional) is a type of number
  top_fastest = var.top_fastest
  # top_slowest - (optional) is a type of number
  top_slowest = var.top_slowest
  # traffic_replication_mirror - (optional) is a type of number
  traffic_replication_mirror = var.traffic_replication_mirror
  # traffic_replication_mirror_da_repl - (optional) is a type of number
  traffic_replication_mirror_da_repl = var.traffic_replication_mirror_da_repl
  # traffic_replication_mirror_ip_repl - (optional) is a type of number
  traffic_replication_mirror_ip_repl = var.traffic_replication_mirror_ip_repl
  # traffic_replication_mirror_sa_da_repl - (optional) is a type of number
  traffic_replication_mirror_sa_da_repl = var.traffic_replication_mirror_sa_da_repl
  # traffic_replication_mirror_sa_repl - (optional) is a type of number
  traffic_replication_mirror_sa_repl = var.traffic_replication_mirror_sa_repl
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "member_list" {
    for_each = var.member_list
    content {
      # fqdn_name - (optional) is a type of string
      fqdn_name = member_list.value["fqdn_name"]
      # host - (optional) is a type of string
      host = member_list.value["host"]
      # member_priority - (optional) is a type of number
      member_priority = member_list.value["member_priority"]
      # member_state - (optional) is a type of string
      member_state = member_list.value["member_state"]
      # member_stats_data_disable - (optional) is a type of number
      member_stats_data_disable = member_list.value["member_stats_data_disable"]
      # member_template - (optional) is a type of string
      member_template = member_list.value["member_template"]
      # name - (optional) is a type of string
      name = member_list.value["name"]
      # port - (optional) is a type of number
      port = member_list.value["port"]
      # resolve_as - (optional) is a type of string
      resolve_as = member_list.value["resolve_as"]
      # server_ipv6_addr - (optional) is a type of string
      server_ipv6_addr = member_list.value["server_ipv6_addr"]
      # user_tag - (optional) is a type of string
      user_tag = member_list.value["user_tag"]
      # uuid - (optional) is a type of string
      uuid = member_list.value["uuid"]

      dynamic "sampling_enable" {
        for_each = member_list.value.sampling_enable
        content {
          # counters1 - (optional) is a type of string
          counters1 = sampling_enable.value["counters1"]
        }
      }

    }
  }

  dynamic "priorities" {
    for_each = var.priorities
    content {
      # priority - (optional) is a type of number
      priority = priorities.value["priority"]
      # priority_action - (optional) is a type of string
      priority_action = priorities.value["priority_action"]
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
  value       = thunder_service_group.this.id
}

output "this" {
  value = thunder_service_group.this
}
```

[top](#index)