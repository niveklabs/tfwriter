# avi_serviceenginegroup

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/avi/d/avi_serviceenginegroup"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_serviceenginegroup" "this" {
  cloud_ref  = var.cloud_ref
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "accelerated_networking" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.accelerated_networking
}

output "active_standby" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.active_standby
}

output "aggressive_failure_detection" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.aggressive_failure_detection
}

output "algo" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.algo
}

output "allow_burst" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.allow_burst
}

output "app_cache_percent" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.app_cache_percent
}

output "app_learning_memory_percent" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.app_learning_memory_percent
}

output "archive_shm_limit" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.archive_shm_limit
}

output "async_ssl" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.async_ssl
}

output "async_ssl_threads" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.async_ssl_threads
}

output "auto_rebalance" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.auto_rebalance
}

output "auto_rebalance_capacity_per_se" {
  description = "returns a list of number"
  value       = data.avi_serviceenginegroup.this.auto_rebalance_capacity_per_se
}

output "auto_rebalance_criteria" {
  description = "returns a list of string"
  value       = data.avi_serviceenginegroup.this.auto_rebalance_criteria
}

output "auto_rebalance_interval" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.auto_rebalance_interval
}

output "auto_redistribute_active_standby_load" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.auto_redistribute_active_standby_load
}

output "bgp_state_update_interval" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.bgp_state_update_interval
}

output "buffer_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.buffer_se
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.cloud_ref
}

output "compress_ip_rules_for_each_ns_subnet" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.compress_ip_rules_for_each_ns_subnet
}

output "config_debugs_on_all_cores" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.config_debugs_on_all_cores
}

output "connection_memory_percentage" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.connection_memory_percentage
}

output "core_shm_app_cache" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.core_shm_app_cache
}

output "core_shm_app_learning" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.core_shm_app_learning
}

output "cpu_reserve" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.cpu_reserve
}

output "cpu_socket_affinity" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.cpu_socket_affinity
}

output "custom_securitygroups_data" {
  description = "returns a list of string"
  value       = data.avi_serviceenginegroup.this.custom_securitygroups_data
}

output "custom_securitygroups_mgmt" {
  description = "returns a list of string"
  value       = data.avi_serviceenginegroup.this.custom_securitygroups_mgmt
}

output "custom_tag" {
  description = "returns a list of object"
  value       = data.avi_serviceenginegroup.this.custom_tag
}

output "data_network_id" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.data_network_id
}

output "datascript_timeout" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.datascript_timeout
}

output "dedicated_dispatcher_core" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.dedicated_dispatcher_core
}

output "description" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.description
}

output "disable_avi_securitygroups" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.disable_avi_securitygroups
}

output "disable_csum_offloads" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.disable_csum_offloads
}

output "disable_gro" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.disable_gro
}

output "disable_se_memory_check" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.disable_se_memory_check
}

output "disable_tso" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.disable_tso
}

output "disk_per_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.disk_per_se
}

output "distribute_load_active_standby" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.distribute_load_active_standby
}

output "distribute_queues" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.distribute_queues
}

output "distribute_vnics" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.distribute_vnics
}

output "enable_gratarp_permanent" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.enable_gratarp_permanent
}

output "enable_hsm_priming" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.enable_hsm_priming
}

output "enable_multi_lb" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.enable_multi_lb
}

output "enable_pcap_tx_ring" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.enable_pcap_tx_ring
}

output "ephemeral_portrange_end" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.ephemeral_portrange_end
}

output "ephemeral_portrange_start" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.ephemeral_portrange_start
}

output "extra_config_multiplier" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.extra_config_multiplier
}

output "extra_shared_config_memory" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.extra_shared_config_memory
}

output "flow_table_new_syn_max_entries" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.flow_table_new_syn_max_entries
}

output "free_list_size" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.free_list_size
}

output "gratarp_permanent_periodicity" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.gratarp_permanent_periodicity
}

output "ha_mode" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.ha_mode
}

output "hardwaresecuritymodulegroup_ref" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.hardwaresecuritymodulegroup_ref
}

output "heap_minimum_config_memory" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.heap_minimum_config_memory
}

output "hm_on_standby" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.hm_on_standby
}

output "host_attribute_key" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.host_attribute_key
}

output "host_attribute_value" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.host_attribute_value
}

output "host_gateway_monitor" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.host_gateway_monitor
}

output "hypervisor" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.id
}

output "ignore_rtt_threshold" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.ignore_rtt_threshold
}

output "ingress_access_data" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.ingress_access_data
}

output "ingress_access_mgmt" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.ingress_access_mgmt
}

output "instance_flavor" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.instance_flavor
}

output "iptables" {
  description = "returns a list of object"
  value       = data.avi_serviceenginegroup.this.iptables
}

output "least_load_core_selection" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.least_load_core_selection
}

output "license_tier" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.license_tier
}

output "license_type" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.license_type
}

output "log_disksz" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.log_disksz
}

output "max_concurrent_external_hm" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_concurrent_external_hm
}

output "max_cpu_usage" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_cpu_usage
}

output "max_memory_per_mempool" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_memory_per_mempool
}

output "max_public_ips_per_lb" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_public_ips_per_lb
}

output "max_queues_per_vnic" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_queues_per_vnic
}

output "max_rules_per_lb" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_rules_per_lb
}

output "max_scaleout_per_vs" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_scaleout_per_vs
}

output "max_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_se
}

output "max_vs_per_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.max_vs_per_se
}

output "mem_reserve" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.mem_reserve
}

output "memory_for_config_update" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.memory_for_config_update
}

output "memory_per_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.memory_per_se
}

output "mgmt_network_ref" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.mgmt_network_ref
}

output "mgmt_subnet" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.mgmt_subnet
}

output "min_cpu_usage" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.min_cpu_usage
}

output "min_scaleout_per_vs" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.min_scaleout_per_vs
}

output "min_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.min_se
}

output "minimum_connection_memory" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.minimum_connection_memory
}

output "n_log_streaming_threads" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.n_log_streaming_threads
}

output "name" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.name
}

output "non_significant_log_throttle" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.non_significant_log_throttle
}

output "num_dispatcher_cores" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.num_dispatcher_cores
}

output "num_flow_cores_sum_changes_to_ignore" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.num_flow_cores_sum_changes_to_ignore
}

output "openstack_availability_zones" {
  description = "returns a list of string"
  value       = data.avi_serviceenginegroup.this.openstack_availability_zones
}

output "openstack_mgmt_network_name" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.openstack_mgmt_network_name
}

output "openstack_mgmt_network_uuid" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.openstack_mgmt_network_uuid
}

output "os_reserved_memory" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.os_reserved_memory
}

output "pcap_tx_mode" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.pcap_tx_mode
}

output "per_app" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.per_app
}

output "placement_mode" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.placement_mode
}

output "realtime_se_metrics" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.realtime_se_metrics
}

output "reboot_on_panic" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.reboot_on_panic
}

output "se_bandwidth_type" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.se_bandwidth_type
}

output "se_deprovision_delay" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_deprovision_delay
}

output "se_dos_profile" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.se_dos_profile
}

output "se_dp_vnic_queue_stall_event_sleep" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_dp_vnic_queue_stall_event_sleep
}

output "se_dp_vnic_queue_stall_threshold" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_dp_vnic_queue_stall_threshold
}

output "se_dp_vnic_queue_stall_timeout" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_dp_vnic_queue_stall_timeout
}

output "se_dp_vnic_restart_on_queue_stall_count" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_dp_vnic_restart_on_queue_stall_count
}

output "se_dp_vnic_stall_se_restart_window" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_dp_vnic_stall_se_restart_window
}

output "se_dpdk_pmd" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_dpdk_pmd
}

output "se_flow_probe_retries" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_flow_probe_retries
}

output "se_flow_probe_retry_timer" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_flow_probe_retry_timer
}

output "se_ipc_udp_port" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_ipc_udp_port
}

output "se_kni_burst_factor" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_kni_burst_factor
}

output "se_lro" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.se_lro
}

output "se_mtu" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_mtu
}

output "se_name_prefix" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.se_name_prefix
}

output "se_pcap_lookahead" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.se_pcap_lookahead
}

output "se_pcap_pkt_count" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_pcap_pkt_count
}

output "se_pcap_pkt_sz" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_pcap_pkt_sz
}

output "se_pcap_qdisc_bypass" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.se_pcap_qdisc_bypass
}

output "se_pcap_reinit_frequency" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_pcap_reinit_frequency
}

output "se_pcap_reinit_threshold" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_pcap_reinit_threshold
}

output "se_probe_port" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_probe_port
}

output "se_remote_punt_udp_port" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_remote_punt_udp_port
}

output "se_rl_prop" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.se_rl_prop
}

output "se_rum_sampling_nav_interval" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_rum_sampling_nav_interval
}

output "se_rum_sampling_nav_percent" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_rum_sampling_nav_percent
}

output "se_rum_sampling_res_interval" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_rum_sampling_res_interval
}

output "se_rum_sampling_res_percent" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_rum_sampling_res_percent
}

output "se_sb_dedicated_core" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.se_sb_dedicated_core
}

output "se_sb_threads" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_sb_threads
}

output "se_thread_multiplier" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_thread_multiplier
}

output "se_tracert_port_range" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.se_tracert_port_range
}

output "se_tunnel_mode" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_tunnel_mode
}

output "se_tunnel_udp_port" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_tunnel_udp_port
}

output "se_tx_batch_size" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_tx_batch_size
}

output "se_udp_encap_ipc" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_udp_encap_ipc
}

output "se_use_dpdk" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_use_dpdk
}

output "se_vs_hb_max_pkts_in_batch" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_vs_hb_max_pkts_in_batch
}

output "se_vs_hb_max_vs_in_pkt" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.se_vs_hb_max_vs_in_pkt
}

output "self_se_election" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.self_se_election
}

output "service_ip6_subnets" {
  description = "returns a list of object"
  value       = data.avi_serviceenginegroup.this.service_ip6_subnets
}

output "service_ip_subnets" {
  description = "returns a list of object"
  value       = data.avi_serviceenginegroup.this.service_ip_subnets
}

output "shm_minimum_config_memory" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.shm_minimum_config_memory
}

output "significant_log_throttle" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.significant_log_throttle
}

output "ssl_preprocess_sni_hostname" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.ssl_preprocess_sni_hostname
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.tenant_ref
}

output "udf_log_throttle" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.udf_log_throttle
}

output "use_standard_alb" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.use_standard_alb
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.uuid
}

output "vcenter_clusters" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.vcenter_clusters
}

output "vcenter_datastore_mode" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.vcenter_datastore_mode
}

output "vcenter_datastores" {
  description = "returns a list of object"
  value       = data.avi_serviceenginegroup.this.vcenter_datastores
}

output "vcenter_datastores_include" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.vcenter_datastores_include
}

output "vcenter_folder" {
  description = "returns a string"
  value       = data.avi_serviceenginegroup.this.vcenter_folder
}

output "vcenter_hosts" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.vcenter_hosts
}

output "vcpus_per_se" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vcpus_per_se
}

output "vip_asg" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.vip_asg
}

output "vs_host_redundancy" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.vs_host_redundancy
}

output "vs_scalein_timeout" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vs_scalein_timeout
}

output "vs_scalein_timeout_for_upgrade" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vs_scalein_timeout_for_upgrade
}

output "vs_scaleout_timeout" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vs_scaleout_timeout
}

output "vs_se_scaleout_additional_wait_time" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vs_se_scaleout_additional_wait_time
}

output "vs_se_scaleout_ready_timeout" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vs_se_scaleout_ready_timeout
}

output "vs_switchover_timeout" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.vs_switchover_timeout
}

output "vss_placement" {
  description = "returns a set of object"
  value       = data.avi_serviceenginegroup.this.vss_placement
}

output "vss_placement_enabled" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.vss_placement_enabled
}

output "waf_mempool" {
  description = "returns a bool"
  value       = data.avi_serviceenginegroup.this.waf_mempool
}

output "waf_mempool_size" {
  description = "returns a number"
  value       = data.avi_serviceenginegroup.this.waf_mempool_size
}

output "this" {
  value = avi_serviceenginegroup.this
}
```

[top](#index)