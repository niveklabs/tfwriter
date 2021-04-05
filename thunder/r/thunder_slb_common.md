# thunder_slb_common

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
module "thunder_slb_common" {
  source = "./modules/thunder/r/thunder_slb_common"

  # after_disable - (optional) is a type of number
  after_disable = null
  # auto_nat_no_ip_refresh - (optional) is a type of string
  auto_nat_no_ip_refresh = null
  # buff_thresh - (optional) is a type of number
  buff_thresh = null
  # buff_thresh_hw_buff - (optional) is a type of number
  buff_thresh_hw_buff = null
  # buff_thresh_relieve_thresh - (optional) is a type of number
  buff_thresh_relieve_thresh = null
  # buff_thresh_sys_buff_high - (optional) is a type of number
  buff_thresh_sys_buff_high = null
  # buff_thresh_sys_buff_low - (optional) is a type of number
  buff_thresh_sys_buff_low = null
  # compress_block_size - (optional) is a type of number
  compress_block_size = null
  # disable_adaptive_resource_check - (optional) is a type of number
  disable_adaptive_resource_check = null
  # disable_server_auto_reselect - (optional) is a type of number
  disable_server_auto_reselect = null
  # dns_cache_age - (optional) is a type of number
  dns_cache_age = null
  # dns_cache_enable - (optional) is a type of number
  dns_cache_enable = null
  # dns_cache_entry_size - (optional) is a type of number
  dns_cache_entry_size = null
  # dns_vip_stateless - (optional) is a type of number
  dns_vip_stateless = null
  # drop_icmp_to_vip_when_vip_down - (optional) is a type of number
  drop_icmp_to_vip_when_vip_down = null
  # dsr_health_check_enable - (optional) is a type of number
  dsr_health_check_enable = null
  # enable_l7_req_acct - (optional) is a type of number
  enable_l7_req_acct = null
  # entity - (optional) is a type of string
  entity = null
  # exclude_destination - (optional) is a type of string
  exclude_destination = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # fast_path_disable - (optional) is a type of number
  fast_path_disable = null
  # gateway_health_check - (optional) is a type of number
  gateway_health_check = null
  # graceful_shutdown - (optional) is a type of number
  graceful_shutdown = null
  # graceful_shutdown_enable - (optional) is a type of number
  graceful_shutdown_enable = null
  # honor_server_response_ttl - (optional) is a type of number
  honor_server_response_ttl = null
  # hw_compression - (optional) is a type of number
  hw_compression = null
  # hw_syn_rr - (optional) is a type of number
  hw_syn_rr = null
  # interval - (optional) is a type of number
  interval = null
  # l2l3_trunk_lb_disable - (optional) is a type of number
  l2l3_trunk_lb_disable = null
  # log_for_reset_unknown_conn - (optional) is a type of number
  log_for_reset_unknown_conn = null
  # low_latency - (optional) is a type of number
  low_latency = null
  # max_buff_queued_per_conn - (optional) is a type of number
  max_buff_queued_per_conn = null
  # max_http_header_count - (optional) is a type of number
  max_http_header_count = null
  # max_local_rate - (optional) is a type of number
  max_local_rate = null
  # max_remote_rate - (optional) is a type of number
  max_remote_rate = null
  # msl_time - (optional) is a type of number
  msl_time = null
  # mss_table - (optional) is a type of number
  mss_table = null
  # no_auto_up_on_aflex - (optional) is a type of number
  no_auto_up_on_aflex = null
  # override_port - (optional) is a type of number
  override_port = null
  # pkt_rate_for_reset_unknown_conn - (optional) is a type of number
  pkt_rate_for_reset_unknown_conn = null
  # player_id_check_enable - (optional) is a type of number
  player_id_check_enable = null
  # range - (optional) is a type of number
  range = null
  # range_end - (optional) is a type of number
  range_end = null
  # range_start - (optional) is a type of number
  range_start = null
  # rate_limit_logging - (optional) is a type of number
  rate_limit_logging = null
  # reset_stale_session - (optional) is a type of number
  reset_stale_session = null
  # resolve_port_conflict - (optional) is a type of number
  resolve_port_conflict = null
  # response_type - (optional) is a type of string
  response_type = null
  # scale_out - (optional) is a type of number
  scale_out = null
  # snat_gwy_for_l3 - (optional) is a type of number
  snat_gwy_for_l3 = null
  # snat_on_vip - (optional) is a type of number
  snat_on_vip = null
  # software - (optional) is a type of number
  software = null
  # sort_res - (optional) is a type of number
  sort_res = null
  # ssli_sni_hash_enable - (optional) is a type of number
  ssli_sni_hash_enable = null
  # stateless_sg_multi_binding - (optional) is a type of number
  stateless_sg_multi_binding = null
  # stats_data_disable - (optional) is a type of number
  stats_data_disable = null
  # timeout - (optional) is a type of number
  timeout = null
  # ttl_threshold - (optional) is a type of number
  ttl_threshold = null
  # use_mss_tab - (optional) is a type of number
  use_mss_tab = null
  # uuid - (optional) is a type of string
  uuid = null

  conn_rate_limit = [{
    src_ip_list = [{
      exceed_action = null
      limit         = null
      limit_period  = null
      lock_out      = null
      log           = null
      protocol      = null
      shared        = null
      uuid          = null
    }]
  }]

  ddos_protection = [{
    ipd_enable_toggle = null
    logging = [{
      ipd_logging_toggle = null
    }]
    packets_per_second = [{
      ipd_tcp = null
      ipd_udp = null
    }]
  }]

  dns_response_rate_limiting = [{
    max_table_entries = null
    uuid              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "after_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_nat_no_ip_refresh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "buff_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "buff_thresh_hw_buff" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "buff_thresh_relieve_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "buff_thresh_sys_buff_high" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "buff_thresh_sys_buff_low" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compress_block_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_adaptive_resource_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_server_auto_reselect" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_cache_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_cache_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_cache_entry_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_vip_stateless" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "drop_icmp_to_vip_when_vip_down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dsr_health_check_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_l7_req_acct" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "entity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exclude_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_stats" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fast_path_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gateway_health_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "graceful_shutdown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "graceful_shutdown_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "honor_server_response_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hw_compression" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hw_syn_rr" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l2l3_trunk_lb_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_for_reset_unknown_conn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "low_latency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_buff_queued_per_conn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_http_header_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_local_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_remote_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "msl_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mss_table" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "no_auto_up_on_aflex" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "override_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pkt_rate_for_reset_unknown_conn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "player_id_check_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "range" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "range_end" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "range_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rate_limit_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_stale_session" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resolve_port_conflict" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "response_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scale_out" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat_gwy_for_l3" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat_on_vip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "software" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sort_res" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssli_sni_hash_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stateless_sg_multi_binding" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stats_data_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ttl_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_mss_tab" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conn_rate_limit" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      src_ip_list = list(object(
        {
          exceed_action = number
          limit         = number
          limit_period  = string
          lock_out      = number
          log           = number
          protocol      = string
          shared        = number
          uuid          = string
        }
      ))
    }
  ))
  default = []
}

variable "ddos_protection" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ipd_enable_toggle = string
      logging = list(object(
        {
          ipd_logging_toggle = string
        }
      ))
      packets_per_second = list(object(
        {
          ipd_tcp = number
          ipd_udp = number
        }
      ))
    }
  ))
  default = []
}

variable "dns_response_rate_limiting" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_table_entries = number
      uuid              = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_common" "this" {
  after_disable                   = var.after_disable
  auto_nat_no_ip_refresh          = var.auto_nat_no_ip_refresh
  buff_thresh                     = var.buff_thresh
  buff_thresh_hw_buff             = var.buff_thresh_hw_buff
  buff_thresh_relieve_thresh      = var.buff_thresh_relieve_thresh
  buff_thresh_sys_buff_high       = var.buff_thresh_sys_buff_high
  buff_thresh_sys_buff_low        = var.buff_thresh_sys_buff_low
  compress_block_size             = var.compress_block_size
  disable_adaptive_resource_check = var.disable_adaptive_resource_check
  disable_server_auto_reselect    = var.disable_server_auto_reselect
  dns_cache_age                   = var.dns_cache_age
  dns_cache_enable                = var.dns_cache_enable
  dns_cache_entry_size            = var.dns_cache_entry_size
  dns_vip_stateless               = var.dns_vip_stateless
  drop_icmp_to_vip_when_vip_down  = var.drop_icmp_to_vip_when_vip_down
  dsr_health_check_enable         = var.dsr_health_check_enable
  enable_l7_req_acct              = var.enable_l7_req_acct
  entity                          = var.entity
  exclude_destination             = var.exclude_destination
  extended_stats                  = var.extended_stats
  fast_path_disable               = var.fast_path_disable
  gateway_health_check            = var.gateway_health_check
  graceful_shutdown               = var.graceful_shutdown
  graceful_shutdown_enable        = var.graceful_shutdown_enable
  honor_server_response_ttl       = var.honor_server_response_ttl
  hw_compression                  = var.hw_compression
  hw_syn_rr                       = var.hw_syn_rr
  interval                        = var.interval
  l2l3_trunk_lb_disable           = var.l2l3_trunk_lb_disable
  log_for_reset_unknown_conn      = var.log_for_reset_unknown_conn
  low_latency                     = var.low_latency
  max_buff_queued_per_conn        = var.max_buff_queued_per_conn
  max_http_header_count           = var.max_http_header_count
  max_local_rate                  = var.max_local_rate
  max_remote_rate                 = var.max_remote_rate
  msl_time                        = var.msl_time
  mss_table                       = var.mss_table
  no_auto_up_on_aflex             = var.no_auto_up_on_aflex
  override_port                   = var.override_port
  pkt_rate_for_reset_unknown_conn = var.pkt_rate_for_reset_unknown_conn
  player_id_check_enable          = var.player_id_check_enable
  range                           = var.range
  range_end                       = var.range_end
  range_start                     = var.range_start
  rate_limit_logging              = var.rate_limit_logging
  reset_stale_session             = var.reset_stale_session
  resolve_port_conflict           = var.resolve_port_conflict
  response_type                   = var.response_type
  scale_out                       = var.scale_out
  snat_gwy_for_l3                 = var.snat_gwy_for_l3
  snat_on_vip                     = var.snat_on_vip
  software                        = var.software
  sort_res                        = var.sort_res
  ssli_sni_hash_enable            = var.ssli_sni_hash_enable
  stateless_sg_multi_binding      = var.stateless_sg_multi_binding
  stats_data_disable              = var.stats_data_disable
  timeout                         = var.timeout
  ttl_threshold                   = var.ttl_threshold
  use_mss_tab                     = var.use_mss_tab
  uuid                            = var.uuid

  dynamic "conn_rate_limit" {
    for_each = var.conn_rate_limit
    content {

      dynamic "src_ip_list" {
        for_each = conn_rate_limit.value.src_ip_list
        content {
          exceed_action = src_ip_list.value["exceed_action"]
          limit         = src_ip_list.value["limit"]
          limit_period  = src_ip_list.value["limit_period"]
          lock_out      = src_ip_list.value["lock_out"]
          log           = src_ip_list.value["log"]
          protocol      = src_ip_list.value["protocol"]
          shared        = src_ip_list.value["shared"]
          uuid          = src_ip_list.value["uuid"]
        }
      }

    }
  }

  dynamic "ddos_protection" {
    for_each = var.ddos_protection
    content {
      ipd_enable_toggle = ddos_protection.value["ipd_enable_toggle"]

      dynamic "logging" {
        for_each = ddos_protection.value.logging
        content {
          ipd_logging_toggle = logging.value["ipd_logging_toggle"]
        }
      }

      dynamic "packets_per_second" {
        for_each = ddos_protection.value.packets_per_second
        content {
          ipd_tcp = packets_per_second.value["ipd_tcp"]
          ipd_udp = packets_per_second.value["ipd_udp"]
        }
      }

    }
  }

  dynamic "dns_response_rate_limiting" {
    for_each = var.dns_response_rate_limiting
    content {
      max_table_entries = dns_response_rate_limiting.value["max_table_entries"]
      uuid              = dns_response_rate_limiting.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_common.this.id
}

output "this" {
  value = thunder_slb_common.this
}
```

[top](#index)