# avi_serviceenginegroup

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
module "avi_serviceenginegroup" {
  source = "./modules/avi/r/avi_serviceenginegroup"

  # accelerated_networking - (optional) is a type of bool
  accelerated_networking = null
  # active_standby - (optional) is a type of bool
  active_standby = null
  # aggressive_failure_detection - (optional) is a type of bool
  aggressive_failure_detection = null
  # algo - (optional) is a type of string
  algo = null
  # allow_burst - (optional) is a type of bool
  allow_burst = null
  # app_cache_percent - (optional) is a type of number
  app_cache_percent = null
  # app_learning_memory_percent - (optional) is a type of number
  app_learning_memory_percent = null
  # archive_shm_limit - (optional) is a type of number
  archive_shm_limit = null
  # async_ssl - (optional) is a type of bool
  async_ssl = null
  # async_ssl_threads - (optional) is a type of number
  async_ssl_threads = null
  # auto_rebalance - (optional) is a type of bool
  auto_rebalance = null
  # auto_rebalance_capacity_per_se - (optional) is a type of list of number
  auto_rebalance_capacity_per_se = []
  # auto_rebalance_criteria - (optional) is a type of list of string
  auto_rebalance_criteria = []
  # auto_rebalance_interval - (optional) is a type of number
  auto_rebalance_interval = null
  # auto_redistribute_active_standby_load - (optional) is a type of bool
  auto_redistribute_active_standby_load = null
  # bgp_state_update_interval - (optional) is a type of number
  bgp_state_update_interval = null
  # buffer_se - (optional) is a type of number
  buffer_se = null
  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # compress_ip_rules_for_each_ns_subnet - (optional) is a type of bool
  compress_ip_rules_for_each_ns_subnet = null
  # config_debugs_on_all_cores - (optional) is a type of bool
  config_debugs_on_all_cores = null
  # connection_memory_percentage - (optional) is a type of number
  connection_memory_percentage = null
  # core_shm_app_cache - (optional) is a type of bool
  core_shm_app_cache = null
  # core_shm_app_learning - (optional) is a type of bool
  core_shm_app_learning = null
  # cpu_reserve - (optional) is a type of bool
  cpu_reserve = null
  # cpu_socket_affinity - (optional) is a type of bool
  cpu_socket_affinity = null
  # custom_securitygroups_data - (optional) is a type of list of string
  custom_securitygroups_data = []
  # custom_securitygroups_mgmt - (optional) is a type of list of string
  custom_securitygroups_mgmt = []
  # data_network_id - (optional) is a type of string
  data_network_id = null
  # datascript_timeout - (optional) is a type of number
  datascript_timeout = null
  # dedicated_dispatcher_core - (optional) is a type of bool
  dedicated_dispatcher_core = null
  # description - (optional) is a type of string
  description = null
  # disable_avi_securitygroups - (optional) is a type of bool
  disable_avi_securitygroups = null
  # disable_csum_offloads - (optional) is a type of bool
  disable_csum_offloads = null
  # disable_gro - (optional) is a type of bool
  disable_gro = null
  # disable_se_memory_check - (optional) is a type of bool
  disable_se_memory_check = null
  # disable_tso - (optional) is a type of bool
  disable_tso = null
  # disk_per_se - (optional) is a type of number
  disk_per_se = null
  # distribute_load_active_standby - (optional) is a type of bool
  distribute_load_active_standby = null
  # distribute_queues - (optional) is a type of bool
  distribute_queues = null
  # distribute_vnics - (optional) is a type of bool
  distribute_vnics = null
  # enable_gratarp_permanent - (optional) is a type of bool
  enable_gratarp_permanent = null
  # enable_hsm_priming - (optional) is a type of bool
  enable_hsm_priming = null
  # enable_multi_lb - (optional) is a type of bool
  enable_multi_lb = null
  # enable_pcap_tx_ring - (optional) is a type of bool
  enable_pcap_tx_ring = null
  # ephemeral_portrange_end - (optional) is a type of number
  ephemeral_portrange_end = null
  # ephemeral_portrange_start - (optional) is a type of number
  ephemeral_portrange_start = null
  # extra_config_multiplier - (optional) is a type of number
  extra_config_multiplier = null
  # extra_shared_config_memory - (optional) is a type of number
  extra_shared_config_memory = null
  # flow_table_new_syn_max_entries - (optional) is a type of number
  flow_table_new_syn_max_entries = null
  # free_list_size - (optional) is a type of number
  free_list_size = null
  # gratarp_permanent_periodicity - (optional) is a type of number
  gratarp_permanent_periodicity = null
  # ha_mode - (optional) is a type of string
  ha_mode = null
  # hardwaresecuritymodulegroup_ref - (optional) is a type of string
  hardwaresecuritymodulegroup_ref = null
  # heap_minimum_config_memory - (optional) is a type of number
  heap_minimum_config_memory = null
  # hm_on_standby - (optional) is a type of bool
  hm_on_standby = null
  # host_attribute_key - (optional) is a type of string
  host_attribute_key = null
  # host_attribute_value - (optional) is a type of string
  host_attribute_value = null
  # host_gateway_monitor - (optional) is a type of bool
  host_gateway_monitor = null
  # hypervisor - (optional) is a type of string
  hypervisor = null
  # ignore_rtt_threshold - (optional) is a type of number
  ignore_rtt_threshold = null
  # ingress_access_data - (optional) is a type of string
  ingress_access_data = null
  # ingress_access_mgmt - (optional) is a type of string
  ingress_access_mgmt = null
  # instance_flavor - (optional) is a type of string
  instance_flavor = null
  # least_load_core_selection - (optional) is a type of bool
  least_load_core_selection = null
  # license_tier - (optional) is a type of string
  license_tier = null
  # license_type - (optional) is a type of string
  license_type = null
  # log_disksz - (optional) is a type of number
  log_disksz = null
  # max_concurrent_external_hm - (optional) is a type of number
  max_concurrent_external_hm = null
  # max_cpu_usage - (optional) is a type of number
  max_cpu_usage = null
  # max_memory_per_mempool - (optional) is a type of number
  max_memory_per_mempool = null
  # max_public_ips_per_lb - (optional) is a type of number
  max_public_ips_per_lb = null
  # max_queues_per_vnic - (optional) is a type of number
  max_queues_per_vnic = null
  # max_rules_per_lb - (optional) is a type of number
  max_rules_per_lb = null
  # max_scaleout_per_vs - (optional) is a type of number
  max_scaleout_per_vs = null
  # max_se - (optional) is a type of number
  max_se = null
  # max_vs_per_se - (optional) is a type of number
  max_vs_per_se = null
  # mem_reserve - (optional) is a type of bool
  mem_reserve = null
  # memory_for_config_update - (optional) is a type of number
  memory_for_config_update = null
  # memory_per_se - (optional) is a type of number
  memory_per_se = null
  # mgmt_network_ref - (optional) is a type of string
  mgmt_network_ref = null
  # min_cpu_usage - (optional) is a type of number
  min_cpu_usage = null
  # min_scaleout_per_vs - (optional) is a type of number
  min_scaleout_per_vs = null
  # min_se - (optional) is a type of number
  min_se = null
  # minimum_connection_memory - (optional) is a type of number
  minimum_connection_memory = null
  # n_log_streaming_threads - (optional) is a type of number
  n_log_streaming_threads = null
  # name - (required) is a type of string
  name = null
  # non_significant_log_throttle - (optional) is a type of number
  non_significant_log_throttle = null
  # num_dispatcher_cores - (optional) is a type of number
  num_dispatcher_cores = null
  # num_flow_cores_sum_changes_to_ignore - (optional) is a type of number
  num_flow_cores_sum_changes_to_ignore = null
  # openstack_availability_zones - (optional) is a type of list of string
  openstack_availability_zones = []
  # openstack_mgmt_network_name - (optional) is a type of string
  openstack_mgmt_network_name = null
  # openstack_mgmt_network_uuid - (optional) is a type of string
  openstack_mgmt_network_uuid = null
  # os_reserved_memory - (optional) is a type of number
  os_reserved_memory = null
  # pcap_tx_mode - (optional) is a type of string
  pcap_tx_mode = null
  # per_app - (optional) is a type of bool
  per_app = null
  # placement_mode - (optional) is a type of string
  placement_mode = null
  # reboot_on_panic - (optional) is a type of bool
  reboot_on_panic = null
  # se_bandwidth_type - (optional) is a type of string
  se_bandwidth_type = null
  # se_deprovision_delay - (optional) is a type of number
  se_deprovision_delay = null
  # se_dp_vnic_queue_stall_event_sleep - (optional) is a type of number
  se_dp_vnic_queue_stall_event_sleep = null
  # se_dp_vnic_queue_stall_threshold - (optional) is a type of number
  se_dp_vnic_queue_stall_threshold = null
  # se_dp_vnic_queue_stall_timeout - (optional) is a type of number
  se_dp_vnic_queue_stall_timeout = null
  # se_dp_vnic_restart_on_queue_stall_count - (optional) is a type of number
  se_dp_vnic_restart_on_queue_stall_count = null
  # se_dp_vnic_stall_se_restart_window - (optional) is a type of number
  se_dp_vnic_stall_se_restart_window = null
  # se_dpdk_pmd - (optional) is a type of number
  se_dpdk_pmd = null
  # se_flow_probe_retries - (optional) is a type of number
  se_flow_probe_retries = null
  # se_flow_probe_retry_timer - (optional) is a type of number
  se_flow_probe_retry_timer = null
  # se_ipc_udp_port - (optional) is a type of number
  se_ipc_udp_port = null
  # se_kni_burst_factor - (optional) is a type of number
  se_kni_burst_factor = null
  # se_lro - (optional) is a type of bool
  se_lro = null
  # se_mtu - (optional) is a type of number
  se_mtu = null
  # se_name_prefix - (optional) is a type of string
  se_name_prefix = null
  # se_pcap_lookahead - (optional) is a type of bool
  se_pcap_lookahead = null
  # se_pcap_pkt_count - (optional) is a type of number
  se_pcap_pkt_count = null
  # se_pcap_pkt_sz - (optional) is a type of number
  se_pcap_pkt_sz = null
  # se_pcap_qdisc_bypass - (optional) is a type of bool
  se_pcap_qdisc_bypass = null
  # se_pcap_reinit_frequency - (optional) is a type of number
  se_pcap_reinit_frequency = null
  # se_pcap_reinit_threshold - (optional) is a type of number
  se_pcap_reinit_threshold = null
  # se_probe_port - (optional) is a type of number
  se_probe_port = null
  # se_remote_punt_udp_port - (optional) is a type of number
  se_remote_punt_udp_port = null
  # se_rum_sampling_nav_interval - (optional) is a type of number
  se_rum_sampling_nav_interval = null
  # se_rum_sampling_nav_percent - (optional) is a type of number
  se_rum_sampling_nav_percent = null
  # se_rum_sampling_res_interval - (optional) is a type of number
  se_rum_sampling_res_interval = null
  # se_rum_sampling_res_percent - (optional) is a type of number
  se_rum_sampling_res_percent = null
  # se_sb_dedicated_core - (optional) is a type of bool
  se_sb_dedicated_core = null
  # se_sb_threads - (optional) is a type of number
  se_sb_threads = null
  # se_thread_multiplier - (optional) is a type of number
  se_thread_multiplier = null
  # se_tunnel_mode - (optional) is a type of number
  se_tunnel_mode = null
  # se_tunnel_udp_port - (optional) is a type of number
  se_tunnel_udp_port = null
  # se_tx_batch_size - (optional) is a type of number
  se_tx_batch_size = null
  # se_udp_encap_ipc - (optional) is a type of number
  se_udp_encap_ipc = null
  # se_use_dpdk - (optional) is a type of number
  se_use_dpdk = null
  # se_vs_hb_max_pkts_in_batch - (optional) is a type of number
  se_vs_hb_max_pkts_in_batch = null
  # se_vs_hb_max_vs_in_pkt - (optional) is a type of number
  se_vs_hb_max_vs_in_pkt = null
  # self_se_election - (optional) is a type of bool
  self_se_election = null
  # shm_minimum_config_memory - (optional) is a type of number
  shm_minimum_config_memory = null
  # significant_log_throttle - (optional) is a type of number
  significant_log_throttle = null
  # ssl_preprocess_sni_hostname - (optional) is a type of bool
  ssl_preprocess_sni_hostname = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # udf_log_throttle - (optional) is a type of number
  udf_log_throttle = null
  # use_standard_alb - (optional) is a type of bool
  use_standard_alb = null
  # uuid - (optional) is a type of string
  uuid = null
  # vcenter_datastore_mode - (optional) is a type of string
  vcenter_datastore_mode = null
  # vcenter_datastores_include - (optional) is a type of bool
  vcenter_datastores_include = null
  # vcenter_folder - (optional) is a type of string
  vcenter_folder = null
  # vcpus_per_se - (optional) is a type of number
  vcpus_per_se = null
  # vs_host_redundancy - (optional) is a type of bool
  vs_host_redundancy = null
  # vs_scalein_timeout - (optional) is a type of number
  vs_scalein_timeout = null
  # vs_scalein_timeout_for_upgrade - (optional) is a type of number
  vs_scalein_timeout_for_upgrade = null
  # vs_scaleout_timeout - (optional) is a type of number
  vs_scaleout_timeout = null
  # vs_se_scaleout_additional_wait_time - (optional) is a type of number
  vs_se_scaleout_additional_wait_time = null
  # vs_se_scaleout_ready_timeout - (optional) is a type of number
  vs_se_scaleout_ready_timeout = null
  # vs_switchover_timeout - (optional) is a type of number
  vs_switchover_timeout = null
  # vss_placement_enabled - (optional) is a type of bool
  vss_placement_enabled = null
  # waf_mempool - (optional) is a type of bool
  waf_mempool = null
  # waf_mempool_size - (optional) is a type of number
  waf_mempool_size = null

  custom_tag = [{
    tag_key = null
    tag_val = null
  }]

  iptables = [{
    chain = null
    rules = [{
      action = null
      dnat_ip = [{
        addr = null
        type = null
      }]
      dst_ip = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      dst_port = [{
        end   = null
        start = null
      }]
      input_interface  = null
      output_interface = null
      proto            = null
      src_ip = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      src_port = [{
        end   = null
        start = null
      }]
      tag = null
    }]
    table = null
  }]

  mgmt_subnet = [{
    ip_addr = [{
      addr = null
      type = null
    }]
    mask = null
  }]

  realtime_se_metrics = [{
    duration = null
    enabled  = null
  }]

  se_dos_profile = [{
    thresh_info = [{
      attack    = null
      max_value = null
      min_value = null
    }]
    thresh_period = null
  }]

  se_rl_prop = [{
    msf_num_stages = null
    msf_stage_size = null
  }]

  se_tracert_port_range = [{
    end   = null
    start = null
  }]

  service_ip6_subnets = [{
    ip_addr = [{
      addr = null
      type = null
    }]
    mask = null
  }]

  service_ip_subnets = [{
    ip_addr = [{
      addr = null
      type = null
    }]
    mask = null
  }]

  vcenter_clusters = [{
    cluster_refs = []
    include      = null
  }]

  vcenter_datastores = [{
    datastore_name = null
  }]

  vcenter_hosts = [{
    host_refs = []
    include   = null
  }]

  vip_asg = [{
    configuration = [{
      zones = [{
        subnet_uuid = null
      }]
    }]
    policy = [{
      dns_cooldown = null
      max_size     = null
      min_size     = null
      suspend      = null
    }]
  }]

  vss_placement = [{
    core_nonaffinity = null
    num_subcores     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accelerated_networking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "active_standby" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "aggressive_failure_detection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "algo" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_burst" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "app_cache_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "app_learning_memory_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "archive_shm_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "async_ssl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "async_ssl_threads" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_rebalance" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_rebalance_capacity_per_se" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "auto_rebalance_criteria" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "auto_rebalance_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_redistribute_active_standby_load" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bgp_state_update_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "buffer_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compress_ip_rules_for_each_ns_subnet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "config_debugs_on_all_cores" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "connection_memory_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_shm_app_cache" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "core_shm_app_learning" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cpu_reserve" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cpu_socket_affinity" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "custom_securitygroups_data" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "custom_securitygroups_mgmt" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "data_network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datascript_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dedicated_dispatcher_core" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_avi_securitygroups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_csum_offloads" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_gro" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_se_memory_check" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_tso" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disk_per_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distribute_load_active_standby" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "distribute_queues" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "distribute_vnics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_gratarp_permanent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_hsm_priming" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_multi_lb" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_pcap_tx_ring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ephemeral_portrange_end" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ephemeral_portrange_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extra_config_multiplier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extra_shared_config_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flow_table_new_syn_max_entries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "free_list_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gratarp_permanent_periodicity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ha_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hardwaresecuritymodulegroup_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heap_minimum_config_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hm_on_standby" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "host_attribute_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_attribute_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_gateway_monitor" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hypervisor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_rtt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ingress_access_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ingress_access_mgmt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_flavor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "least_load_core_selection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_disksz" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_concurrent_external_hm" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_cpu_usage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_memory_per_mempool" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_public_ips_per_lb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_queues_per_vnic" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_rules_per_lb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_scaleout_per_vs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_vs_per_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mem_reserve" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "memory_for_config_update" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "memory_per_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mgmt_network_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_cpu_usage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_scaleout_per_vs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minimum_connection_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "n_log_streaming_threads" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "non_significant_log_throttle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "num_dispatcher_cores" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "num_flow_cores_sum_changes_to_ignore" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "openstack_availability_zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "openstack_mgmt_network_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "openstack_mgmt_network_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_reserved_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pcap_tx_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_app" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "placement_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reboot_on_panic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_bandwidth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_deprovision_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_dp_vnic_queue_stall_event_sleep" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_dp_vnic_queue_stall_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_dp_vnic_queue_stall_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_dp_vnic_restart_on_queue_stall_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_dp_vnic_stall_se_restart_window" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_dpdk_pmd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_flow_probe_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_flow_probe_retry_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_ipc_udp_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_kni_burst_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_lro" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_pcap_lookahead" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_pcap_pkt_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_pcap_pkt_sz" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_pcap_qdisc_bypass" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_pcap_reinit_frequency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_pcap_reinit_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_probe_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_remote_punt_udp_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_rum_sampling_nav_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_rum_sampling_nav_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_rum_sampling_res_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_rum_sampling_res_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_sb_dedicated_core" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_sb_threads" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_thread_multiplier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_tunnel_mode" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_tunnel_udp_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_tx_batch_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_udp_encap_ipc" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_use_dpdk" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_vs_hb_max_pkts_in_batch" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_vs_hb_max_vs_in_pkt" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "self_se_election" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shm_minimum_config_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "significant_log_throttle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_preprocess_sni_hostname" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "udf_log_throttle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_standard_alb" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcenter_datastore_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcenter_datastores_include" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vcenter_folder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcpus_per_se" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_host_redundancy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vs_scalein_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_scalein_timeout_for_upgrade" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_scaleout_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_scaleout_additional_wait_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_scaleout_ready_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_switchover_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vss_placement_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "waf_mempool" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "waf_mempool_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "custom_tag" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      tag_key = string
      tag_val = string
    }
  ))
  default = []
}

variable "iptables" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      chain = string
      rules = list(object(
        {
          action = string
          dnat_ip = set(object(
            {
              addr = string
              type = string
            }
          ))
          dst_ip = set(object(
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
          dst_port = set(object(
            {
              end   = number
              start = number
            }
          ))
          input_interface  = string
          output_interface = string
          proto            = string
          src_ip = set(object(
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
          src_port = set(object(
            {
              end   = number
              start = number
            }
          ))
          tag = string
        }
      ))
      table = string
    }
  ))
  default = []
}

variable "mgmt_subnet" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}

variable "realtime_se_metrics" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      duration = number
      enabled  = bool
    }
  ))
  default = []
}

variable "se_dos_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}

variable "se_rl_prop" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      msf_num_stages = number
      msf_stage_size = number
    }
  ))
  default = []
}

variable "se_tracert_port_range" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      end   = number
      start = number
    }
  ))
  default = []
}

variable "service_ip6_subnets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}

variable "service_ip_subnets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}

variable "vcenter_clusters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cluster_refs = list(string)
      include      = bool
    }
  ))
  default = []
}

variable "vcenter_datastores" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      datastore_name = string
    }
  ))
  default = []
}

variable "vcenter_hosts" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      host_refs = list(string)
      include   = bool
    }
  ))
  default = []
}

variable "vip_asg" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      configuration = set(object(
        {
          zones = list(object(
            {
              subnet_uuid = string
            }
          ))
        }
      ))
      policy = set(object(
        {
          dns_cooldown = number
          max_size     = number
          min_size     = number
          suspend      = bool
        }
      ))
    }
  ))
  default = []
}

variable "vss_placement" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      core_nonaffinity = number
      num_subcores     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_serviceenginegroup" "this" {
  accelerated_networking                  = var.accelerated_networking
  active_standby                          = var.active_standby
  aggressive_failure_detection            = var.aggressive_failure_detection
  algo                                    = var.algo
  allow_burst                             = var.allow_burst
  app_cache_percent                       = var.app_cache_percent
  app_learning_memory_percent             = var.app_learning_memory_percent
  archive_shm_limit                       = var.archive_shm_limit
  async_ssl                               = var.async_ssl
  async_ssl_threads                       = var.async_ssl_threads
  auto_rebalance                          = var.auto_rebalance
  auto_rebalance_capacity_per_se          = var.auto_rebalance_capacity_per_se
  auto_rebalance_criteria                 = var.auto_rebalance_criteria
  auto_rebalance_interval                 = var.auto_rebalance_interval
  auto_redistribute_active_standby_load   = var.auto_redistribute_active_standby_load
  bgp_state_update_interval               = var.bgp_state_update_interval
  buffer_se                               = var.buffer_se
  cloud_ref                               = var.cloud_ref
  compress_ip_rules_for_each_ns_subnet    = var.compress_ip_rules_for_each_ns_subnet
  config_debugs_on_all_cores              = var.config_debugs_on_all_cores
  connection_memory_percentage            = var.connection_memory_percentage
  core_shm_app_cache                      = var.core_shm_app_cache
  core_shm_app_learning                   = var.core_shm_app_learning
  cpu_reserve                             = var.cpu_reserve
  cpu_socket_affinity                     = var.cpu_socket_affinity
  custom_securitygroups_data              = var.custom_securitygroups_data
  custom_securitygroups_mgmt              = var.custom_securitygroups_mgmt
  data_network_id                         = var.data_network_id
  datascript_timeout                      = var.datascript_timeout
  dedicated_dispatcher_core               = var.dedicated_dispatcher_core
  description                             = var.description
  disable_avi_securitygroups              = var.disable_avi_securitygroups
  disable_csum_offloads                   = var.disable_csum_offloads
  disable_gro                             = var.disable_gro
  disable_se_memory_check                 = var.disable_se_memory_check
  disable_tso                             = var.disable_tso
  disk_per_se                             = var.disk_per_se
  distribute_load_active_standby          = var.distribute_load_active_standby
  distribute_queues                       = var.distribute_queues
  distribute_vnics                        = var.distribute_vnics
  enable_gratarp_permanent                = var.enable_gratarp_permanent
  enable_hsm_priming                      = var.enable_hsm_priming
  enable_multi_lb                         = var.enable_multi_lb
  enable_pcap_tx_ring                     = var.enable_pcap_tx_ring
  ephemeral_portrange_end                 = var.ephemeral_portrange_end
  ephemeral_portrange_start               = var.ephemeral_portrange_start
  extra_config_multiplier                 = var.extra_config_multiplier
  extra_shared_config_memory              = var.extra_shared_config_memory
  flow_table_new_syn_max_entries          = var.flow_table_new_syn_max_entries
  free_list_size                          = var.free_list_size
  gratarp_permanent_periodicity           = var.gratarp_permanent_periodicity
  ha_mode                                 = var.ha_mode
  hardwaresecuritymodulegroup_ref         = var.hardwaresecuritymodulegroup_ref
  heap_minimum_config_memory              = var.heap_minimum_config_memory
  hm_on_standby                           = var.hm_on_standby
  host_attribute_key                      = var.host_attribute_key
  host_attribute_value                    = var.host_attribute_value
  host_gateway_monitor                    = var.host_gateway_monitor
  hypervisor                              = var.hypervisor
  ignore_rtt_threshold                    = var.ignore_rtt_threshold
  ingress_access_data                     = var.ingress_access_data
  ingress_access_mgmt                     = var.ingress_access_mgmt
  instance_flavor                         = var.instance_flavor
  least_load_core_selection               = var.least_load_core_selection
  license_tier                            = var.license_tier
  license_type                            = var.license_type
  log_disksz                              = var.log_disksz
  max_concurrent_external_hm              = var.max_concurrent_external_hm
  max_cpu_usage                           = var.max_cpu_usage
  max_memory_per_mempool                  = var.max_memory_per_mempool
  max_public_ips_per_lb                   = var.max_public_ips_per_lb
  max_queues_per_vnic                     = var.max_queues_per_vnic
  max_rules_per_lb                        = var.max_rules_per_lb
  max_scaleout_per_vs                     = var.max_scaleout_per_vs
  max_se                                  = var.max_se
  max_vs_per_se                           = var.max_vs_per_se
  mem_reserve                             = var.mem_reserve
  memory_for_config_update                = var.memory_for_config_update
  memory_per_se                           = var.memory_per_se
  mgmt_network_ref                        = var.mgmt_network_ref
  min_cpu_usage                           = var.min_cpu_usage
  min_scaleout_per_vs                     = var.min_scaleout_per_vs
  min_se                                  = var.min_se
  minimum_connection_memory               = var.minimum_connection_memory
  n_log_streaming_threads                 = var.n_log_streaming_threads
  name                                    = var.name
  non_significant_log_throttle            = var.non_significant_log_throttle
  num_dispatcher_cores                    = var.num_dispatcher_cores
  num_flow_cores_sum_changes_to_ignore    = var.num_flow_cores_sum_changes_to_ignore
  openstack_availability_zones            = var.openstack_availability_zones
  openstack_mgmt_network_name             = var.openstack_mgmt_network_name
  openstack_mgmt_network_uuid             = var.openstack_mgmt_network_uuid
  os_reserved_memory                      = var.os_reserved_memory
  pcap_tx_mode                            = var.pcap_tx_mode
  per_app                                 = var.per_app
  placement_mode                          = var.placement_mode
  reboot_on_panic                         = var.reboot_on_panic
  se_bandwidth_type                       = var.se_bandwidth_type
  se_deprovision_delay                    = var.se_deprovision_delay
  se_dp_vnic_queue_stall_event_sleep      = var.se_dp_vnic_queue_stall_event_sleep
  se_dp_vnic_queue_stall_threshold        = var.se_dp_vnic_queue_stall_threshold
  se_dp_vnic_queue_stall_timeout          = var.se_dp_vnic_queue_stall_timeout
  se_dp_vnic_restart_on_queue_stall_count = var.se_dp_vnic_restart_on_queue_stall_count
  se_dp_vnic_stall_se_restart_window      = var.se_dp_vnic_stall_se_restart_window
  se_dpdk_pmd                             = var.se_dpdk_pmd
  se_flow_probe_retries                   = var.se_flow_probe_retries
  se_flow_probe_retry_timer               = var.se_flow_probe_retry_timer
  se_ipc_udp_port                         = var.se_ipc_udp_port
  se_kni_burst_factor                     = var.se_kni_burst_factor
  se_lro                                  = var.se_lro
  se_mtu                                  = var.se_mtu
  se_name_prefix                          = var.se_name_prefix
  se_pcap_lookahead                       = var.se_pcap_lookahead
  se_pcap_pkt_count                       = var.se_pcap_pkt_count
  se_pcap_pkt_sz                          = var.se_pcap_pkt_sz
  se_pcap_qdisc_bypass                    = var.se_pcap_qdisc_bypass
  se_pcap_reinit_frequency                = var.se_pcap_reinit_frequency
  se_pcap_reinit_threshold                = var.se_pcap_reinit_threshold
  se_probe_port                           = var.se_probe_port
  se_remote_punt_udp_port                 = var.se_remote_punt_udp_port
  se_rum_sampling_nav_interval            = var.se_rum_sampling_nav_interval
  se_rum_sampling_nav_percent             = var.se_rum_sampling_nav_percent
  se_rum_sampling_res_interval            = var.se_rum_sampling_res_interval
  se_rum_sampling_res_percent             = var.se_rum_sampling_res_percent
  se_sb_dedicated_core                    = var.se_sb_dedicated_core
  se_sb_threads                           = var.se_sb_threads
  se_thread_multiplier                    = var.se_thread_multiplier
  se_tunnel_mode                          = var.se_tunnel_mode
  se_tunnel_udp_port                      = var.se_tunnel_udp_port
  se_tx_batch_size                        = var.se_tx_batch_size
  se_udp_encap_ipc                        = var.se_udp_encap_ipc
  se_use_dpdk                             = var.se_use_dpdk
  se_vs_hb_max_pkts_in_batch              = var.se_vs_hb_max_pkts_in_batch
  se_vs_hb_max_vs_in_pkt                  = var.se_vs_hb_max_vs_in_pkt
  self_se_election                        = var.self_se_election
  shm_minimum_config_memory               = var.shm_minimum_config_memory
  significant_log_throttle                = var.significant_log_throttle
  ssl_preprocess_sni_hostname             = var.ssl_preprocess_sni_hostname
  tenant_ref                              = var.tenant_ref
  udf_log_throttle                        = var.udf_log_throttle
  use_standard_alb                        = var.use_standard_alb
  uuid                                    = var.uuid
  vcenter_datastore_mode                  = var.vcenter_datastore_mode
  vcenter_datastores_include              = var.vcenter_datastores_include
  vcenter_folder                          = var.vcenter_folder
  vcpus_per_se                            = var.vcpus_per_se
  vs_host_redundancy                      = var.vs_host_redundancy
  vs_scalein_timeout                      = var.vs_scalein_timeout
  vs_scalein_timeout_for_upgrade          = var.vs_scalein_timeout_for_upgrade
  vs_scaleout_timeout                     = var.vs_scaleout_timeout
  vs_se_scaleout_additional_wait_time     = var.vs_se_scaleout_additional_wait_time
  vs_se_scaleout_ready_timeout            = var.vs_se_scaleout_ready_timeout
  vs_switchover_timeout                   = var.vs_switchover_timeout
  vss_placement_enabled                   = var.vss_placement_enabled
  waf_mempool                             = var.waf_mempool
  waf_mempool_size                        = var.waf_mempool_size

  dynamic "custom_tag" {
    for_each = var.custom_tag
    content {
      tag_key = custom_tag.value["tag_key"]
      tag_val = custom_tag.value["tag_val"]
    }
  }

  dynamic "iptables" {
    for_each = var.iptables
    content {
      chain = iptables.value["chain"]
      table = iptables.value["table"]

      dynamic "rules" {
        for_each = iptables.value.rules
        content {
          action           = rules.value["action"]
          input_interface  = rules.value["input_interface"]
          output_interface = rules.value["output_interface"]
          proto            = rules.value["proto"]
          tag              = rules.value["tag"]

          dynamic "dnat_ip" {
            for_each = rules.value.dnat_ip
            content {
              addr = dnat_ip.value["addr"]
              type = dnat_ip.value["type"]
            }
          }

          dynamic "dst_ip" {
            for_each = rules.value.dst_ip
            content {
              mask = dst_ip.value["mask"]

              dynamic "ip_addr" {
                for_each = dst_ip.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "dst_port" {
            for_each = rules.value.dst_port
            content {
              end   = dst_port.value["end"]
              start = dst_port.value["start"]
            }
          }

          dynamic "src_ip" {
            for_each = rules.value.src_ip
            content {
              mask = src_ip.value["mask"]

              dynamic "ip_addr" {
                for_each = src_ip.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "src_port" {
            for_each = rules.value.src_port
            content {
              end   = src_port.value["end"]
              start = src_port.value["start"]
            }
          }

        }
      }

    }
  }

  dynamic "mgmt_subnet" {
    for_each = var.mgmt_subnet
    content {
      mask = mgmt_subnet.value["mask"]

      dynamic "ip_addr" {
        for_each = mgmt_subnet.value.ip_addr
        content {
          addr = ip_addr.value["addr"]
          type = ip_addr.value["type"]
        }
      }

    }
  }

  dynamic "realtime_se_metrics" {
    for_each = var.realtime_se_metrics
    content {
      duration = realtime_se_metrics.value["duration"]
      enabled  = realtime_se_metrics.value["enabled"]
    }
  }

  dynamic "se_dos_profile" {
    for_each = var.se_dos_profile
    content {
      thresh_period = se_dos_profile.value["thresh_period"]

      dynamic "thresh_info" {
        for_each = se_dos_profile.value.thresh_info
        content {
          attack    = thresh_info.value["attack"]
          max_value = thresh_info.value["max_value"]
          min_value = thresh_info.value["min_value"]
        }
      }

    }
  }

  dynamic "se_rl_prop" {
    for_each = var.se_rl_prop
    content {
      msf_num_stages = se_rl_prop.value["msf_num_stages"]
      msf_stage_size = se_rl_prop.value["msf_stage_size"]
    }
  }

  dynamic "se_tracert_port_range" {
    for_each = var.se_tracert_port_range
    content {
      end   = se_tracert_port_range.value["end"]
      start = se_tracert_port_range.value["start"]
    }
  }

  dynamic "service_ip6_subnets" {
    for_each = var.service_ip6_subnets
    content {
      mask = service_ip6_subnets.value["mask"]

      dynamic "ip_addr" {
        for_each = service_ip6_subnets.value.ip_addr
        content {
          addr = ip_addr.value["addr"]
          type = ip_addr.value["type"]
        }
      }

    }
  }

  dynamic "service_ip_subnets" {
    for_each = var.service_ip_subnets
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

  dynamic "vcenter_clusters" {
    for_each = var.vcenter_clusters
    content {
      cluster_refs = vcenter_clusters.value["cluster_refs"]
      include      = vcenter_clusters.value["include"]
    }
  }

  dynamic "vcenter_datastores" {
    for_each = var.vcenter_datastores
    content {
      datastore_name = vcenter_datastores.value["datastore_name"]
    }
  }

  dynamic "vcenter_hosts" {
    for_each = var.vcenter_hosts
    content {
      host_refs = vcenter_hosts.value["host_refs"]
      include   = vcenter_hosts.value["include"]
    }
  }

  dynamic "vip_asg" {
    for_each = var.vip_asg
    content {

      dynamic "configuration" {
        for_each = vip_asg.value.configuration
        content {

          dynamic "zones" {
            for_each = configuration.value.zones
            content {
              subnet_uuid = zones.value["subnet_uuid"]
            }
          }

        }
      }

      dynamic "policy" {
        for_each = vip_asg.value.policy
        content {
          dns_cooldown = policy.value["dns_cooldown"]
          max_size     = policy.value["max_size"]
          min_size     = policy.value["min_size"]
          suspend      = policy.value["suspend"]
        }
      }

    }
  }

  dynamic "vss_placement" {
    for_each = var.vss_placement
    content {
      core_nonaffinity = vss_placement.value["core_nonaffinity"]
      num_subcores     = vss_placement.value["num_subcores"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accelerated_networking" {
  description = "returns a bool"
  value       = avi_serviceenginegroup.this.accelerated_networking
}

output "allow_burst" {
  description = "returns a bool"
  value       = avi_serviceenginegroup.this.allow_burst
}

output "cloud_ref" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.cloud_ref
}

output "data_network_id" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.data_network_id
}

output "description" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.description
}

output "enable_pcap_tx_ring" {
  description = "returns a bool"
  value       = avi_serviceenginegroup.this.enable_pcap_tx_ring
}

output "ephemeral_portrange_end" {
  description = "returns a number"
  value       = avi_serviceenginegroup.this.ephemeral_portrange_end
}

output "ephemeral_portrange_start" {
  description = "returns a number"
  value       = avi_serviceenginegroup.this.ephemeral_portrange_start
}

output "hardwaresecuritymodulegroup_ref" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.hardwaresecuritymodulegroup_ref
}

output "host_attribute_key" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.host_attribute_key
}

output "host_attribute_value" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.host_attribute_value
}

output "hypervisor" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.id
}

output "instance_flavor" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.instance_flavor
}

output "license_tier" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.license_tier
}

output "license_type" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.license_type
}

output "max_concurrent_external_hm" {
  description = "returns a number"
  value       = avi_serviceenginegroup.this.max_concurrent_external_hm
}

output "mgmt_network_ref" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.mgmt_network_ref
}

output "openstack_mgmt_network_name" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.openstack_mgmt_network_name
}

output "openstack_mgmt_network_uuid" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.openstack_mgmt_network_uuid
}

output "se_bandwidth_type" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.se_bandwidth_type
}

output "se_mtu" {
  description = "returns a number"
  value       = avi_serviceenginegroup.this.se_mtu
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.tenant_ref
}

output "use_standard_alb" {
  description = "returns a bool"
  value       = avi_serviceenginegroup.this.use_standard_alb
}

output "uuid" {
  description = "returns a string"
  value       = avi_serviceenginegroup.this.uuid
}

output "this" {
  value = avi_serviceenginegroup.this
}
```

[top](#index)