# avi_seproperties

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_seproperties" {
  source = "./modules/avi/r/avi_seproperties"

  # uuid - (optional) is a type of string
  uuid = null

  se_agent_properties = [{
    controller_echo_miss_aggressive_limit  = null
    controller_echo_miss_limit             = null
    controller_echo_rpc_aggressive_timeout = null
    controller_echo_rpc_timeout            = null
    controller_heartbeat_miss_limit        = null
    controller_heartbeat_timeout_sec       = null
    controller_registration_timeout_sec    = null
    controller_rpc_timeout                 = null
    cpustats_interval                      = null
    ctrl_reg_pending_max_wait_time         = null
    debug_mode                             = null
    dp_aggressive_deq_interval_msec        = null
    dp_aggressive_enq_interval_msec        = null
    dp_batch_size                          = null
    dp_deq_interval_msec                   = null
    dp_enq_interval_msec                   = null
    dp_max_wait_rsp_time_sec               = null
    dp_reg_pending_max_wait_time           = null
    headless_timeout_sec                   = null
    ignore_docker_mac_change               = null
    ns_helper_deq_interval_msec            = null
    sdb_flush_interval                     = null
    sdb_pipeline_size                      = null
    sdb_scan_count                         = null
    se_grp_change_disruptive               = null
    seagent_statecache_properties = [{
      sc_batch_buffer_flush_limit       = null
      sc_shard_cleanup_max_time         = null
      sc_state_ring_batch_dequeue_limit = null
      sc_states_flush_interval          = null
      sc_stream_check_interval          = null
      sc_thread_q_batch_dequeue_limit   = null
      sc_thread_q_max_size              = null
      sc_thread_sleep_interval          = null
    }]
    send_se_ready_timeout       = null
    states_flush_interval       = null
    vnic_dhcp_ip_check_interval = null
    vnic_dhcp_ip_max_retries    = null
    vnic_ip_delete_interval     = null
    vnic_probe_interval         = null
    vnic_rpc_retry_interval     = null
    vnicdb_cmd_history_size     = null
  }]

  se_bootup_properties = [{
    docker_backend_portend         = null
    docker_backend_portstart       = null
    fair_queueing_enabled          = null
    geo_db_granularity             = null
    l7_conns_per_core              = null
    l7_resvd_listen_conns_per_core = null
    log_agent_debug_enabled        = null
    log_agent_trace_enabled        = null
    se_dp_compression = [{
      buf_num          = null
      buf_size         = null
      hash_size        = null
      level_aggressive = null
      level_normal     = null
      window_size      = null
    }]
    se_emulated_cores                     = null
    se_ip_encap_ipc                       = null
    se_l3_encap_ipc                       = null
    se_log_buffer_app_blocking_dequeue    = null
    se_log_buffer_applog_size             = null
    se_log_buffer_chunk_count             = null
    se_log_buffer_conn_blocking_dequeue   = null
    se_log_buffer_connlog_size            = null
    se_log_buffer_events_blocking_dequeue = null
    se_log_buffer_events_size             = null
    ssl_sess_cache_per_vs                 = null
    ssl_sess_cache_timeout                = null
    tcp_syncache_hashsize                 = null
  }]

  se_runtime_properties = [{
    admin_ssh_enabled = null
    app_headers = [{
      hdr_match_case = null
      hdr_name       = null
      hdr_string_op  = null
    }]
    baremetal_dispatcher_handles_flows           = null
    connections_lossy_log_rate_limiter_threshold = null
    connections_udfnf_log_rate_limiter_threshold = null
    disable_flow_probes                          = null
    dos_profile = [{
      thresh_info = [{
        attack    = null
        max_value = null
        min_value = null
      }]
      thresh_period = null
    }]
    downstream_send_timeout               = null
    dp_aggressive_hb_frequency            = null
    dp_aggressive_hb_timeout_count        = null
    dp_hb_frequency                       = null
    dp_hb_timeout_count                   = null
    dupip_frequency                       = null
    dupip_timeout_count                   = null
    enable_hsm_log                        = null
    feproxy_vips_enable_proxy_arp         = null
    flow_table_batch_push_frequency       = null
    global_mtu                            = null
    http_rum_console_log                  = null
    http_rum_min_content_length           = null
    lbaction_num_requests_to_dispatch     = null
    lbaction_rq_per_request_max_retries   = null
    log_agent_compress_logs               = null
    log_agent_conn_send_buffer_size       = null
    log_agent_export_msg_buffer_size      = null
    log_agent_export_wait_time            = null
    log_agent_file_sz_appl                = null
    log_agent_file_sz_conn                = null
    log_agent_file_sz_debug               = null
    log_agent_file_sz_event               = null
    log_agent_log_storage_min_sz          = null
    log_agent_max_active_adf_files_per_vs = null
    log_agent_max_concurrent_rsync        = null
    log_agent_max_logmessage_proto_sz     = null
    log_agent_max_storage_excess_percent  = null
    log_agent_max_storage_ignore_percent  = null
    log_agent_min_storage_per_vs          = null
    log_agent_pause_interval              = null
    log_agent_sleep_interval              = null
    log_agent_unknown_vs_timer            = null
    log_message_max_file_list_size        = null
    mcache_enabled                        = null
    mcache_fetch_enabled                  = null
    mcache_store_in_enabled               = null
    mcache_store_in_max_size              = null
    mcache_store_in_min_size              = null
    mcache_store_out_enabled              = null
    ngx_free_connection_stack             = null
    persistence_mem_max                   = null
    scaleout_udp_per_pkt                  = null
    se_auth_ldap_bind_timeout             = null
    se_auth_ldap_cache_size               = null
    se_auth_ldap_connect_timeout          = null
    se_auth_ldap_conns_per_server         = null
    se_auth_ldap_reconnect_timeout        = null
    se_auth_ldap_request_timeout          = null
    se_auth_ldap_servers_failover_only    = null
    se_dp_compression = [{
      max_low_rtt  = null
      min_high_rtt = null
      min_length   = null
      mobile_str   = []
    }]
    se_dp_hm_drops                                = null
    se_dp_if_state_poll_interval                  = null
    se_dp_log_nf_enqueue_percent                  = null
    se_dp_log_udf_enqueue_percent                 = null
    se_dump_core_on_assert                        = null
    se_handle_interface_routes                    = null
    se_hb_persist_fudge_bits                      = null
    se_mac_error_threshold_to_disable_promiscious = null
    se_memory_poison                              = null
    se_metrics_interval                           = null
    se_metrics_rt_enabled                         = null
    se_metrics_rt_interval                        = null
    se_packet_buffer_max                          = null
    se_random_tcp_drops                           = null
    se_rate_limiters = [{
      arp_rl        = null
      default_rl    = null
      flow_probe_rl = null
      icmp_rl       = null
      icmp_rsp_rl   = null
      rst_rl        = null
    }]
    service_ip_subnets = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    service_port_ranges = [{
      end   = null
      start = null
    }]
    services_accessible_all_interfaces     = null
    spdy_fwd_proxy_parse_enable            = null
    tcp_syncache_max_retransmit_default    = null
    upstream_connect_timeout               = null
    upstream_connpool_cache_thresh         = null
    upstream_connpool_conn_idle_thresh_tmo = null
    upstream_connpool_core_max_cache       = null
    upstream_connpool_enable               = null
    upstream_connpool_strategy             = null
    upstream_keepalive                     = null
    upstream_read_timeout                  = null
    upstream_send_timeout                  = null
    user_defined_metric_age                = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_agent_properties" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      controller_echo_miss_aggressive_limit  = number
      controller_echo_miss_limit             = number
      controller_echo_rpc_aggressive_timeout = number
      controller_echo_rpc_timeout            = number
      controller_heartbeat_miss_limit        = number
      controller_heartbeat_timeout_sec       = number
      controller_registration_timeout_sec    = number
      controller_rpc_timeout                 = number
      cpustats_interval                      = number
      ctrl_reg_pending_max_wait_time         = number
      debug_mode                             = bool
      dp_aggressive_deq_interval_msec        = number
      dp_aggressive_enq_interval_msec        = number
      dp_batch_size                          = number
      dp_deq_interval_msec                   = number
      dp_enq_interval_msec                   = number
      dp_max_wait_rsp_time_sec               = number
      dp_reg_pending_max_wait_time           = number
      headless_timeout_sec                   = number
      ignore_docker_mac_change               = bool
      ns_helper_deq_interval_msec            = number
      sdb_flush_interval                     = number
      sdb_pipeline_size                      = number
      sdb_scan_count                         = number
      se_grp_change_disruptive               = bool
      seagent_statecache_properties = set(object(
        {
          sc_batch_buffer_flush_limit       = number
          sc_shard_cleanup_max_time         = number
          sc_state_ring_batch_dequeue_limit = number
          sc_states_flush_interval          = number
          sc_stream_check_interval          = number
          sc_thread_q_batch_dequeue_limit   = number
          sc_thread_q_max_size              = number
          sc_thread_sleep_interval          = number
        }
      ))
      send_se_ready_timeout       = number
      states_flush_interval       = number
      vnic_dhcp_ip_check_interval = number
      vnic_dhcp_ip_max_retries    = number
      vnic_ip_delete_interval     = number
      vnic_probe_interval         = number
      vnic_rpc_retry_interval     = number
      vnicdb_cmd_history_size     = number
    }
  ))
  default = []
}

variable "se_bootup_properties" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      docker_backend_portend         = number
      docker_backend_portstart       = number
      fair_queueing_enabled          = bool
      geo_db_granularity             = number
      l7_conns_per_core              = number
      l7_resvd_listen_conns_per_core = number
      log_agent_debug_enabled        = bool
      log_agent_trace_enabled        = bool
      se_dp_compression = set(object(
        {
          buf_num          = number
          buf_size         = number
          hash_size        = number
          level_aggressive = number
          level_normal     = number
          window_size      = number
        }
      ))
      se_emulated_cores                     = number
      se_ip_encap_ipc                       = number
      se_l3_encap_ipc                       = number
      se_log_buffer_app_blocking_dequeue    = bool
      se_log_buffer_applog_size             = number
      se_log_buffer_chunk_count             = number
      se_log_buffer_conn_blocking_dequeue   = bool
      se_log_buffer_connlog_size            = number
      se_log_buffer_events_blocking_dequeue = bool
      se_log_buffer_events_size             = number
      ssl_sess_cache_per_vs                 = number
      ssl_sess_cache_timeout                = number
      tcp_syncache_hashsize                 = number
    }
  ))
  default = []
}

variable "se_runtime_properties" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      admin_ssh_enabled = bool
      app_headers = list(object(
        {
          hdr_match_case = string
          hdr_name       = string
          hdr_string_op  = string
        }
      ))
      baremetal_dispatcher_handles_flows           = bool
      connections_lossy_log_rate_limiter_threshold = number
      connections_udfnf_log_rate_limiter_threshold = number
      disable_flow_probes                          = bool
      dos_profile = set(object(
        {
          thresh_info = list(object(
            {
              attack    = string
              max_value = number
              min_value = number
            }
          ))
          thresh_period = number
        }
      ))
      downstream_send_timeout               = number
      dp_aggressive_hb_frequency            = number
      dp_aggressive_hb_timeout_count        = number
      dp_hb_frequency                       = number
      dp_hb_timeout_count                   = number
      dupip_frequency                       = number
      dupip_timeout_count                   = number
      enable_hsm_log                        = bool
      feproxy_vips_enable_proxy_arp         = bool
      flow_table_batch_push_frequency       = number
      global_mtu                            = number
      http_rum_console_log                  = bool
      http_rum_min_content_length           = number
      lbaction_num_requests_to_dispatch     = number
      lbaction_rq_per_request_max_retries   = number
      log_agent_compress_logs               = bool
      log_agent_conn_send_buffer_size       = number
      log_agent_export_msg_buffer_size      = number
      log_agent_export_wait_time            = number
      log_agent_file_sz_appl                = number
      log_agent_file_sz_conn                = number
      log_agent_file_sz_debug               = number
      log_agent_file_sz_event               = number
      log_agent_log_storage_min_sz          = number
      log_agent_max_active_adf_files_per_vs = number
      log_agent_max_concurrent_rsync        = number
      log_agent_max_logmessage_proto_sz     = number
      log_agent_max_storage_excess_percent  = number
      log_agent_max_storage_ignore_percent  = number
      log_agent_min_storage_per_vs          = number
      log_agent_pause_interval              = number
      log_agent_sleep_interval              = number
      log_agent_unknown_vs_timer            = number
      log_message_max_file_list_size        = number
      mcache_enabled                        = bool
      mcache_fetch_enabled                  = bool
      mcache_store_in_enabled               = bool
      mcache_store_in_max_size              = number
      mcache_store_in_min_size              = number
      mcache_store_out_enabled              = bool
      ngx_free_connection_stack             = bool
      persistence_mem_max                   = number
      scaleout_udp_per_pkt                  = bool
      se_auth_ldap_bind_timeout             = number
      se_auth_ldap_cache_size               = number
      se_auth_ldap_connect_timeout          = number
      se_auth_ldap_conns_per_server         = number
      se_auth_ldap_reconnect_timeout        = number
      se_auth_ldap_request_timeout          = number
      se_auth_ldap_servers_failover_only    = bool
      se_dp_compression = set(object(
        {
          max_low_rtt  = number
          min_high_rtt = number
          min_length   = number
          mobile_str   = list(string)
        }
      ))
      se_dp_hm_drops                                = number
      se_dp_if_state_poll_interval                  = number
      se_dp_log_nf_enqueue_percent                  = number
      se_dp_log_udf_enqueue_percent                 = number
      se_dump_core_on_assert                        = bool
      se_handle_interface_routes                    = bool
      se_hb_persist_fudge_bits                      = number
      se_mac_error_threshold_to_disable_promiscious = number
      se_memory_poison                              = bool
      se_metrics_interval                           = number
      se_metrics_rt_enabled                         = bool
      se_metrics_rt_interval                        = number
      se_packet_buffer_max                          = number
      se_random_tcp_drops                           = bool
      se_rate_limiters = set(object(
        {
          arp_rl        = number
          default_rl    = number
          flow_probe_rl = number
          icmp_rl       = number
          icmp_rsp_rl   = number
          rst_rl        = number
        }
      ))
      service_ip_subnets = list(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      service_port_ranges = list(object(
        {
          end   = number
          start = number
        }
      ))
      services_accessible_all_interfaces     = bool
      spdy_fwd_proxy_parse_enable            = bool
      tcp_syncache_max_retransmit_default    = number
      upstream_connect_timeout               = number
      upstream_connpool_cache_thresh         = number
      upstream_connpool_conn_idle_thresh_tmo = number
      upstream_connpool_core_max_cache       = number
      upstream_connpool_enable               = bool
      upstream_connpool_strategy             = number
      upstream_keepalive                     = bool
      upstream_read_timeout                  = number
      upstream_send_timeout                  = number
      user_defined_metric_age                = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_seproperties" "this" {
  uuid = var.uuid

  dynamic "se_agent_properties" {
    for_each = var.se_agent_properties
    content {
      controller_echo_miss_aggressive_limit  = se_agent_properties.value["controller_echo_miss_aggressive_limit"]
      controller_echo_miss_limit             = se_agent_properties.value["controller_echo_miss_limit"]
      controller_echo_rpc_aggressive_timeout = se_agent_properties.value["controller_echo_rpc_aggressive_timeout"]
      controller_echo_rpc_timeout            = se_agent_properties.value["controller_echo_rpc_timeout"]
      controller_heartbeat_miss_limit        = se_agent_properties.value["controller_heartbeat_miss_limit"]
      controller_heartbeat_timeout_sec       = se_agent_properties.value["controller_heartbeat_timeout_sec"]
      controller_registration_timeout_sec    = se_agent_properties.value["controller_registration_timeout_sec"]
      controller_rpc_timeout                 = se_agent_properties.value["controller_rpc_timeout"]
      cpustats_interval                      = se_agent_properties.value["cpustats_interval"]
      ctrl_reg_pending_max_wait_time         = se_agent_properties.value["ctrl_reg_pending_max_wait_time"]
      debug_mode                             = se_agent_properties.value["debug_mode"]
      dp_aggressive_deq_interval_msec        = se_agent_properties.value["dp_aggressive_deq_interval_msec"]
      dp_aggressive_enq_interval_msec        = se_agent_properties.value["dp_aggressive_enq_interval_msec"]
      dp_batch_size                          = se_agent_properties.value["dp_batch_size"]
      dp_deq_interval_msec                   = se_agent_properties.value["dp_deq_interval_msec"]
      dp_enq_interval_msec                   = se_agent_properties.value["dp_enq_interval_msec"]
      dp_max_wait_rsp_time_sec               = se_agent_properties.value["dp_max_wait_rsp_time_sec"]
      dp_reg_pending_max_wait_time           = se_agent_properties.value["dp_reg_pending_max_wait_time"]
      headless_timeout_sec                   = se_agent_properties.value["headless_timeout_sec"]
      ignore_docker_mac_change               = se_agent_properties.value["ignore_docker_mac_change"]
      ns_helper_deq_interval_msec            = se_agent_properties.value["ns_helper_deq_interval_msec"]
      sdb_flush_interval                     = se_agent_properties.value["sdb_flush_interval"]
      sdb_pipeline_size                      = se_agent_properties.value["sdb_pipeline_size"]
      sdb_scan_count                         = se_agent_properties.value["sdb_scan_count"]
      se_grp_change_disruptive               = se_agent_properties.value["se_grp_change_disruptive"]
      send_se_ready_timeout                  = se_agent_properties.value["send_se_ready_timeout"]
      states_flush_interval                  = se_agent_properties.value["states_flush_interval"]
      vnic_dhcp_ip_check_interval            = se_agent_properties.value["vnic_dhcp_ip_check_interval"]
      vnic_dhcp_ip_max_retries               = se_agent_properties.value["vnic_dhcp_ip_max_retries"]
      vnic_ip_delete_interval                = se_agent_properties.value["vnic_ip_delete_interval"]
      vnic_probe_interval                    = se_agent_properties.value["vnic_probe_interval"]
      vnic_rpc_retry_interval                = se_agent_properties.value["vnic_rpc_retry_interval"]
      vnicdb_cmd_history_size                = se_agent_properties.value["vnicdb_cmd_history_size"]

      dynamic "seagent_statecache_properties" {
        for_each = se_agent_properties.value.seagent_statecache_properties
        content {
          sc_batch_buffer_flush_limit       = seagent_statecache_properties.value["sc_batch_buffer_flush_limit"]
          sc_shard_cleanup_max_time         = seagent_statecache_properties.value["sc_shard_cleanup_max_time"]
          sc_state_ring_batch_dequeue_limit = seagent_statecache_properties.value["sc_state_ring_batch_dequeue_limit"]
          sc_states_flush_interval          = seagent_statecache_properties.value["sc_states_flush_interval"]
          sc_stream_check_interval          = seagent_statecache_properties.value["sc_stream_check_interval"]
          sc_thread_q_batch_dequeue_limit   = seagent_statecache_properties.value["sc_thread_q_batch_dequeue_limit"]
          sc_thread_q_max_size              = seagent_statecache_properties.value["sc_thread_q_max_size"]
          sc_thread_sleep_interval          = seagent_statecache_properties.value["sc_thread_sleep_interval"]
        }
      }

    }
  }

  dynamic "se_bootup_properties" {
    for_each = var.se_bootup_properties
    content {
      docker_backend_portend                = se_bootup_properties.value["docker_backend_portend"]
      docker_backend_portstart              = se_bootup_properties.value["docker_backend_portstart"]
      fair_queueing_enabled                 = se_bootup_properties.value["fair_queueing_enabled"]
      geo_db_granularity                    = se_bootup_properties.value["geo_db_granularity"]
      l7_conns_per_core                     = se_bootup_properties.value["l7_conns_per_core"]
      l7_resvd_listen_conns_per_core        = se_bootup_properties.value["l7_resvd_listen_conns_per_core"]
      log_agent_debug_enabled               = se_bootup_properties.value["log_agent_debug_enabled"]
      log_agent_trace_enabled               = se_bootup_properties.value["log_agent_trace_enabled"]
      se_emulated_cores                     = se_bootup_properties.value["se_emulated_cores"]
      se_ip_encap_ipc                       = se_bootup_properties.value["se_ip_encap_ipc"]
      se_l3_encap_ipc                       = se_bootup_properties.value["se_l3_encap_ipc"]
      se_log_buffer_app_blocking_dequeue    = se_bootup_properties.value["se_log_buffer_app_blocking_dequeue"]
      se_log_buffer_applog_size             = se_bootup_properties.value["se_log_buffer_applog_size"]
      se_log_buffer_chunk_count             = se_bootup_properties.value["se_log_buffer_chunk_count"]
      se_log_buffer_conn_blocking_dequeue   = se_bootup_properties.value["se_log_buffer_conn_blocking_dequeue"]
      se_log_buffer_connlog_size            = se_bootup_properties.value["se_log_buffer_connlog_size"]
      se_log_buffer_events_blocking_dequeue = se_bootup_properties.value["se_log_buffer_events_blocking_dequeue"]
      se_log_buffer_events_size             = se_bootup_properties.value["se_log_buffer_events_size"]
      ssl_sess_cache_per_vs                 = se_bootup_properties.value["ssl_sess_cache_per_vs"]
      ssl_sess_cache_timeout                = se_bootup_properties.value["ssl_sess_cache_timeout"]
      tcp_syncache_hashsize                 = se_bootup_properties.value["tcp_syncache_hashsize"]

      dynamic "se_dp_compression" {
        for_each = se_bootup_properties.value.se_dp_compression
        content {
          buf_num          = se_dp_compression.value["buf_num"]
          buf_size         = se_dp_compression.value["buf_size"]
          hash_size        = se_dp_compression.value["hash_size"]
          level_aggressive = se_dp_compression.value["level_aggressive"]
          level_normal     = se_dp_compression.value["level_normal"]
          window_size      = se_dp_compression.value["window_size"]
        }
      }

    }
  }

  dynamic "se_runtime_properties" {
    for_each = var.se_runtime_properties
    content {
      admin_ssh_enabled                             = se_runtime_properties.value["admin_ssh_enabled"]
      baremetal_dispatcher_handles_flows            = se_runtime_properties.value["baremetal_dispatcher_handles_flows"]
      connections_lossy_log_rate_limiter_threshold  = se_runtime_properties.value["connections_lossy_log_rate_limiter_threshold"]
      connections_udfnf_log_rate_limiter_threshold  = se_runtime_properties.value["connections_udfnf_log_rate_limiter_threshold"]
      disable_flow_probes                           = se_runtime_properties.value["disable_flow_probes"]
      downstream_send_timeout                       = se_runtime_properties.value["downstream_send_timeout"]
      dp_aggressive_hb_frequency                    = se_runtime_properties.value["dp_aggressive_hb_frequency"]
      dp_aggressive_hb_timeout_count                = se_runtime_properties.value["dp_aggressive_hb_timeout_count"]
      dp_hb_frequency                               = se_runtime_properties.value["dp_hb_frequency"]
      dp_hb_timeout_count                           = se_runtime_properties.value["dp_hb_timeout_count"]
      dupip_frequency                               = se_runtime_properties.value["dupip_frequency"]
      dupip_timeout_count                           = se_runtime_properties.value["dupip_timeout_count"]
      enable_hsm_log                                = se_runtime_properties.value["enable_hsm_log"]
      feproxy_vips_enable_proxy_arp                 = se_runtime_properties.value["feproxy_vips_enable_proxy_arp"]
      flow_table_batch_push_frequency               = se_runtime_properties.value["flow_table_batch_push_frequency"]
      global_mtu                                    = se_runtime_properties.value["global_mtu"]
      http_rum_console_log                          = se_runtime_properties.value["http_rum_console_log"]
      http_rum_min_content_length                   = se_runtime_properties.value["http_rum_min_content_length"]
      lbaction_num_requests_to_dispatch             = se_runtime_properties.value["lbaction_num_requests_to_dispatch"]
      lbaction_rq_per_request_max_retries           = se_runtime_properties.value["lbaction_rq_per_request_max_retries"]
      log_agent_compress_logs                       = se_runtime_properties.value["log_agent_compress_logs"]
      log_agent_conn_send_buffer_size               = se_runtime_properties.value["log_agent_conn_send_buffer_size"]
      log_agent_export_msg_buffer_size              = se_runtime_properties.value["log_agent_export_msg_buffer_size"]
      log_agent_export_wait_time                    = se_runtime_properties.value["log_agent_export_wait_time"]
      log_agent_file_sz_appl                        = se_runtime_properties.value["log_agent_file_sz_appl"]
      log_agent_file_sz_conn                        = se_runtime_properties.value["log_agent_file_sz_conn"]
      log_agent_file_sz_debug                       = se_runtime_properties.value["log_agent_file_sz_debug"]
      log_agent_file_sz_event                       = se_runtime_properties.value["log_agent_file_sz_event"]
      log_agent_log_storage_min_sz                  = se_runtime_properties.value["log_agent_log_storage_min_sz"]
      log_agent_max_active_adf_files_per_vs         = se_runtime_properties.value["log_agent_max_active_adf_files_per_vs"]
      log_agent_max_concurrent_rsync                = se_runtime_properties.value["log_agent_max_concurrent_rsync"]
      log_agent_max_logmessage_proto_sz             = se_runtime_properties.value["log_agent_max_logmessage_proto_sz"]
      log_agent_max_storage_excess_percent          = se_runtime_properties.value["log_agent_max_storage_excess_percent"]
      log_agent_max_storage_ignore_percent          = se_runtime_properties.value["log_agent_max_storage_ignore_percent"]
      log_agent_min_storage_per_vs                  = se_runtime_properties.value["log_agent_min_storage_per_vs"]
      log_agent_pause_interval                      = se_runtime_properties.value["log_agent_pause_interval"]
      log_agent_sleep_interval                      = se_runtime_properties.value["log_agent_sleep_interval"]
      log_agent_unknown_vs_timer                    = se_runtime_properties.value["log_agent_unknown_vs_timer"]
      log_message_max_file_list_size                = se_runtime_properties.value["log_message_max_file_list_size"]
      mcache_enabled                                = se_runtime_properties.value["mcache_enabled"]
      mcache_fetch_enabled                          = se_runtime_properties.value["mcache_fetch_enabled"]
      mcache_store_in_enabled                       = se_runtime_properties.value["mcache_store_in_enabled"]
      mcache_store_in_max_size                      = se_runtime_properties.value["mcache_store_in_max_size"]
      mcache_store_in_min_size                      = se_runtime_properties.value["mcache_store_in_min_size"]
      mcache_store_out_enabled                      = se_runtime_properties.value["mcache_store_out_enabled"]
      ngx_free_connection_stack                     = se_runtime_properties.value["ngx_free_connection_stack"]
      persistence_mem_max                           = se_runtime_properties.value["persistence_mem_max"]
      scaleout_udp_per_pkt                          = se_runtime_properties.value["scaleout_udp_per_pkt"]
      se_auth_ldap_bind_timeout                     = se_runtime_properties.value["se_auth_ldap_bind_timeout"]
      se_auth_ldap_cache_size                       = se_runtime_properties.value["se_auth_ldap_cache_size"]
      se_auth_ldap_connect_timeout                  = se_runtime_properties.value["se_auth_ldap_connect_timeout"]
      se_auth_ldap_conns_per_server                 = se_runtime_properties.value["se_auth_ldap_conns_per_server"]
      se_auth_ldap_reconnect_timeout                = se_runtime_properties.value["se_auth_ldap_reconnect_timeout"]
      se_auth_ldap_request_timeout                  = se_runtime_properties.value["se_auth_ldap_request_timeout"]
      se_auth_ldap_servers_failover_only            = se_runtime_properties.value["se_auth_ldap_servers_failover_only"]
      se_dp_hm_drops                                = se_runtime_properties.value["se_dp_hm_drops"]
      se_dp_if_state_poll_interval                  = se_runtime_properties.value["se_dp_if_state_poll_interval"]
      se_dp_log_nf_enqueue_percent                  = se_runtime_properties.value["se_dp_log_nf_enqueue_percent"]
      se_dp_log_udf_enqueue_percent                 = se_runtime_properties.value["se_dp_log_udf_enqueue_percent"]
      se_dump_core_on_assert                        = se_runtime_properties.value["se_dump_core_on_assert"]
      se_handle_interface_routes                    = se_runtime_properties.value["se_handle_interface_routes"]
      se_hb_persist_fudge_bits                      = se_runtime_properties.value["se_hb_persist_fudge_bits"]
      se_mac_error_threshold_to_disable_promiscious = se_runtime_properties.value["se_mac_error_threshold_to_disable_promiscious"]
      se_memory_poison                              = se_runtime_properties.value["se_memory_poison"]
      se_metrics_interval                           = se_runtime_properties.value["se_metrics_interval"]
      se_metrics_rt_enabled                         = se_runtime_properties.value["se_metrics_rt_enabled"]
      se_metrics_rt_interval                        = se_runtime_properties.value["se_metrics_rt_interval"]
      se_packet_buffer_max                          = se_runtime_properties.value["se_packet_buffer_max"]
      se_random_tcp_drops                           = se_runtime_properties.value["se_random_tcp_drops"]
      services_accessible_all_interfaces            = se_runtime_properties.value["services_accessible_all_interfaces"]
      spdy_fwd_proxy_parse_enable                   = se_runtime_properties.value["spdy_fwd_proxy_parse_enable"]
      tcp_syncache_max_retransmit_default           = se_runtime_properties.value["tcp_syncache_max_retransmit_default"]
      upstream_connect_timeout                      = se_runtime_properties.value["upstream_connect_timeout"]
      upstream_connpool_cache_thresh                = se_runtime_properties.value["upstream_connpool_cache_thresh"]
      upstream_connpool_conn_idle_thresh_tmo        = se_runtime_properties.value["upstream_connpool_conn_idle_thresh_tmo"]
      upstream_connpool_core_max_cache              = se_runtime_properties.value["upstream_connpool_core_max_cache"]
      upstream_connpool_enable                      = se_runtime_properties.value["upstream_connpool_enable"]
      upstream_connpool_strategy                    = se_runtime_properties.value["upstream_connpool_strategy"]
      upstream_keepalive                            = se_runtime_properties.value["upstream_keepalive"]
      upstream_read_timeout                         = se_runtime_properties.value["upstream_read_timeout"]
      upstream_send_timeout                         = se_runtime_properties.value["upstream_send_timeout"]
      user_defined_metric_age                       = se_runtime_properties.value["user_defined_metric_age"]

      dynamic "app_headers" {
        for_each = se_runtime_properties.value.app_headers
        content {
          hdr_match_case = app_headers.value["hdr_match_case"]
          hdr_name       = app_headers.value["hdr_name"]
          hdr_string_op  = app_headers.value["hdr_string_op"]
        }
      }

      dynamic "dos_profile" {
        for_each = se_runtime_properties.value.dos_profile
        content {
          thresh_period = dos_profile.value["thresh_period"]

          dynamic "thresh_info" {
            for_each = dos_profile.value.thresh_info
            content {
              attack    = thresh_info.value["attack"]
              max_value = thresh_info.value["max_value"]
              min_value = thresh_info.value["min_value"]
            }
          }

        }
      }

      dynamic "se_dp_compression" {
        for_each = se_runtime_properties.value.se_dp_compression
        content {
          max_low_rtt  = se_dp_compression.value["max_low_rtt"]
          min_high_rtt = se_dp_compression.value["min_high_rtt"]
          min_length   = se_dp_compression.value["min_length"]
          mobile_str   = se_dp_compression.value["mobile_str"]
        }
      }

      dynamic "se_rate_limiters" {
        for_each = se_runtime_properties.value.se_rate_limiters
        content {
          arp_rl        = se_rate_limiters.value["arp_rl"]
          default_rl    = se_rate_limiters.value["default_rl"]
          flow_probe_rl = se_rate_limiters.value["flow_probe_rl"]
          icmp_rl       = se_rate_limiters.value["icmp_rl"]
          icmp_rsp_rl   = se_rate_limiters.value["icmp_rsp_rl"]
          rst_rl        = se_rate_limiters.value["rst_rl"]
        }
      }

      dynamic "service_ip_subnets" {
        for_each = se_runtime_properties.value.service_ip_subnets
        content {
          mask = service_ip_subnets.value["mask"]

          dynamic "ip_addr" {
            for_each = service_ip_subnets.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "service_port_ranges" {
        for_each = se_runtime_properties.value.service_port_ranges
        content {
          end   = service_port_ranges.value["end"]
          start = service_port_ranges.value["start"]
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
  value       = avi_seproperties.this.id
}

output "uuid" {
  description = "returns a string"
  value       = avi_seproperties.this.uuid
}

output "this" {
  value = avi_seproperties.this
}
```

[top](#index)