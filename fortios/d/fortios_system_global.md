# fortios_system_global

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "fortios_system_global" {
  source = "./modules/fortios/d/fortios_system_global"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_global" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "admin_concurrent" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_concurrent
}

output "admin_console_timeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_console_timeout
}

output "admin_hsts_max_age" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_hsts_max_age
}

output "admin_https_pki_required" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_https_pki_required
}

output "admin_https_redirect" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_https_redirect
}

output "admin_https_ssl_versions" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_https_ssl_versions
}

output "admin_lockout_duration" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_lockout_duration
}

output "admin_lockout_threshold" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_lockout_threshold
}

output "admin_login_max" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_login_max
}

output "admin_maintainer" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_maintainer
}

output "admin_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_port
}

output "admin_restrict_local" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_restrict_local
}

output "admin_scp" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_scp
}

output "admin_server_cert" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_server_cert
}

output "admin_sport" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_sport
}

output "admin_ssh_grace_time" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_ssh_grace_time
}

output "admin_ssh_password" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_ssh_password
}

output "admin_ssh_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_ssh_port
}

output "admin_ssh_v1" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_ssh_v1
}

output "admin_telnet" {
  description = "returns a string"
  value       = data.fortios_system_global.this.admin_telnet
}

output "admin_telnet_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admin_telnet_port
}

output "admintimeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.admintimeout
}

output "alias" {
  description = "returns a string"
  value       = data.fortios_system_global.this.alias
}

output "allow_traffic_redirect" {
  description = "returns a string"
  value       = data.fortios_system_global.this.allow_traffic_redirect
}

output "anti_replay" {
  description = "returns a string"
  value       = data.fortios_system_global.this.anti_replay
}

output "arp_max_entry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.arp_max_entry
}

output "asymroute" {
  description = "returns a string"
  value       = data.fortios_system_global.this.asymroute
}

output "auth_cert" {
  description = "returns a string"
  value       = data.fortios_system_global.this.auth_cert
}

output "auth_http_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.auth_http_port
}

output "auth_https_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.auth_https_port
}

output "auth_keepalive" {
  description = "returns a string"
  value       = data.fortios_system_global.this.auth_keepalive
}

output "auth_session_limit" {
  description = "returns a string"
  value       = data.fortios_system_global.this.auth_session_limit
}

output "auto_auth_extension_device" {
  description = "returns a string"
  value       = data.fortios_system_global.this.auto_auth_extension_device
}

output "autorun_log_fsck" {
  description = "returns a string"
  value       = data.fortios_system_global.this.autorun_log_fsck
}

output "av_affinity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.av_affinity
}

output "av_failopen" {
  description = "returns a string"
  value       = data.fortios_system_global.this.av_failopen
}

output "av_failopen_session" {
  description = "returns a string"
  value       = data.fortios_system_global.this.av_failopen_session
}

output "batch_cmdb" {
  description = "returns a string"
  value       = data.fortios_system_global.this.batch_cmdb
}

output "block_session_timer" {
  description = "returns a number"
  value       = data.fortios_system_global.this.block_session_timer
}

output "br_fdb_max_entry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.br_fdb_max_entry
}

output "cert_chain_max" {
  description = "returns a number"
  value       = data.fortios_system_global.this.cert_chain_max
}

output "cfg_revert_timeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.cfg_revert_timeout
}

output "cfg_save" {
  description = "returns a string"
  value       = data.fortios_system_global.this.cfg_save
}

output "check_protocol_header" {
  description = "returns a string"
  value       = data.fortios_system_global.this.check_protocol_header
}

output "check_reset_range" {
  description = "returns a string"
  value       = data.fortios_system_global.this.check_reset_range
}

output "cli_audit_log" {
  description = "returns a string"
  value       = data.fortios_system_global.this.cli_audit_log
}

output "cloud_communication" {
  description = "returns a string"
  value       = data.fortios_system_global.this.cloud_communication
}

output "clt_cert_req" {
  description = "returns a string"
  value       = data.fortios_system_global.this.clt_cert_req
}

output "compliance_check" {
  description = "returns a string"
  value       = data.fortios_system_global.this.compliance_check
}

output "compliance_check_time" {
  description = "returns a string"
  value       = data.fortios_system_global.this.compliance_check_time
}

output "cpu_use_threshold" {
  description = "returns a number"
  value       = data.fortios_system_global.this.cpu_use_threshold
}

output "csr_ca_attribute" {
  description = "returns a string"
  value       = data.fortios_system_global.this.csr_ca_attribute
}

output "daily_restart" {
  description = "returns a string"
  value       = data.fortios_system_global.this.daily_restart
}

output "default_service_source_port" {
  description = "returns a string"
  value       = data.fortios_system_global.this.default_service_source_port
}

output "device_identification_active_scan_delay" {
  description = "returns a number"
  value       = data.fortios_system_global.this.device_identification_active_scan_delay
}

output "device_idle_timeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.device_idle_timeout
}

output "dh_params" {
  description = "returns a string"
  value       = data.fortios_system_global.this.dh_params
}

output "dnsproxy_worker_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.dnsproxy_worker_count
}

output "dst" {
  description = "returns a string"
  value       = data.fortios_system_global.this.dst
}

output "endpoint_control_fds_access" {
  description = "returns a string"
  value       = data.fortios_system_global.this.endpoint_control_fds_access
}

output "endpoint_control_portal_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.endpoint_control_portal_port
}

output "failtime" {
  description = "returns a number"
  value       = data.fortios_system_global.this.failtime
}

output "faz_disk_buffer_size" {
  description = "returns a number"
  value       = data.fortios_system_global.this.faz_disk_buffer_size
}

output "fds_statistics" {
  description = "returns a string"
  value       = data.fortios_system_global.this.fds_statistics
}

output "fds_statistics_period" {
  description = "returns a number"
  value       = data.fortios_system_global.this.fds_statistics_period
}

output "fec_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.fec_port
}

output "fgd_alert_subscription" {
  description = "returns a string"
  value       = data.fortios_system_global.this.fgd_alert_subscription
}

output "fortiextender" {
  description = "returns a string"
  value       = data.fortios_system_global.this.fortiextender
}

output "fortiextender_data_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.fortiextender_data_port
}

output "fortiextender_vlan_mode" {
  description = "returns a string"
  value       = data.fortios_system_global.this.fortiextender_vlan_mode
}

output "fortiipam_integration" {
  description = "returns a string"
  value       = data.fortios_system_global.this.fortiipam_integration
}

output "fortiservice_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.fortiservice_port
}

output "fortitoken_cloud" {
  description = "returns a string"
  value       = data.fortios_system_global.this.fortitoken_cloud
}

output "gui_allow_default_hostname" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_allow_default_hostname
}

output "gui_certificates" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_certificates
}

output "gui_custom_language" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_custom_language
}

output "gui_date_format" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_date_format
}

output "gui_date_time_source" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_date_time_source
}

output "gui_device_latitude" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_device_latitude
}

output "gui_device_longitude" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_device_longitude
}

output "gui_display_hostname" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_display_hostname
}

output "gui_firmware_upgrade_setup_warning" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_firmware_upgrade_setup_warning
}

output "gui_firmware_upgrade_warning" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_firmware_upgrade_warning
}

output "gui_forticare_registration_setup_warning" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_forticare_registration_setup_warning
}

output "gui_fortigate_cloud_sandbox" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_fortigate_cloud_sandbox
}

output "gui_fortisandbox_cloud" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_fortisandbox_cloud
}

output "gui_ipv6" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_ipv6
}

output "gui_lines_per_page" {
  description = "returns a number"
  value       = data.fortios_system_global.this.gui_lines_per_page
}

output "gui_theme" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_theme
}

output "gui_wireless_opensecurity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.gui_wireless_opensecurity
}

output "honor_df" {
  description = "returns a string"
  value       = data.fortios_system_global.this.honor_df
}

output "hostname" {
  description = "returns a string"
  value       = data.fortios_system_global.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_global.this.id
}

output "igmp_state_limit" {
  description = "returns a number"
  value       = data.fortios_system_global.this.igmp_state_limit
}

output "ike_embryonic_limit" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ike_embryonic_limit
}

output "interval" {
  description = "returns a number"
  value       = data.fortios_system_global.this.interval
}

output "ip_src_port_range" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ip_src_port_range
}

output "ips_affinity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ips_affinity
}

output "ipsec_asic_offload" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ipsec_asic_offload
}

output "ipsec_hmac_offload" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ipsec_hmac_offload
}

output "ipsec_soft_dec_async" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ipsec_soft_dec_async
}

output "ipv6_accept_dad" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ipv6_accept_dad
}

output "ipv6_allow_anycast_probe" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ipv6_allow_anycast_probe
}

output "ipv6_allow_traffic_redirect" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ipv6_allow_traffic_redirect
}

output "irq_time_accounting" {
  description = "returns a string"
  value       = data.fortios_system_global.this.irq_time_accounting
}

output "language" {
  description = "returns a string"
  value       = data.fortios_system_global.this.language
}

output "ldapconntimeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ldapconntimeout
}

output "lldp_reception" {
  description = "returns a string"
  value       = data.fortios_system_global.this.lldp_reception
}

output "lldp_transmission" {
  description = "returns a string"
  value       = data.fortios_system_global.this.lldp_transmission
}

output "log_ssl_connection" {
  description = "returns a string"
  value       = data.fortios_system_global.this.log_ssl_connection
}

output "log_uuid_address" {
  description = "returns a string"
  value       = data.fortios_system_global.this.log_uuid_address
}

output "log_uuid_policy" {
  description = "returns a string"
  value       = data.fortios_system_global.this.log_uuid_policy
}

output "login_timestamp" {
  description = "returns a string"
  value       = data.fortios_system_global.this.login_timestamp
}

output "long_vdom_name" {
  description = "returns a string"
  value       = data.fortios_system_global.this.long_vdom_name
}

output "management_vdom" {
  description = "returns a string"
  value       = data.fortios_system_global.this.management_vdom
}

output "max_dlpstat_memory" {
  description = "returns a number"
  value       = data.fortios_system_global.this.max_dlpstat_memory
}

output "max_route_cache_size" {
  description = "returns a number"
  value       = data.fortios_system_global.this.max_route_cache_size
}

output "mc_ttl_notchange" {
  description = "returns a string"
  value       = data.fortios_system_global.this.mc_ttl_notchange
}

output "memory_use_threshold_extreme" {
  description = "returns a number"
  value       = data.fortios_system_global.this.memory_use_threshold_extreme
}

output "memory_use_threshold_green" {
  description = "returns a number"
  value       = data.fortios_system_global.this.memory_use_threshold_green
}

output "memory_use_threshold_red" {
  description = "returns a number"
  value       = data.fortios_system_global.this.memory_use_threshold_red
}

output "miglog_affinity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.miglog_affinity
}

output "miglogd_children" {
  description = "returns a number"
  value       = data.fortios_system_global.this.miglogd_children
}

output "multi_factor_authentication" {
  description = "returns a string"
  value       = data.fortios_system_global.this.multi_factor_authentication
}

output "multicast_forward" {
  description = "returns a string"
  value       = data.fortios_system_global.this.multicast_forward
}

output "ndp_max_entry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ndp_max_entry
}

output "per_user_bal" {
  description = "returns a string"
  value       = data.fortios_system_global.this.per_user_bal
}

output "per_user_bwl" {
  description = "returns a string"
  value       = data.fortios_system_global.this.per_user_bwl
}

output "policy_auth_concurrent" {
  description = "returns a number"
  value       = data.fortios_system_global.this.policy_auth_concurrent
}

output "post_login_banner" {
  description = "returns a string"
  value       = data.fortios_system_global.this.post_login_banner
}

output "pre_login_banner" {
  description = "returns a string"
  value       = data.fortios_system_global.this.pre_login_banner
}

output "private_data_encryption" {
  description = "returns a string"
  value       = data.fortios_system_global.this.private_data_encryption
}

output "proxy_auth_lifetime" {
  description = "returns a string"
  value       = data.fortios_system_global.this.proxy_auth_lifetime
}

output "proxy_auth_lifetime_timeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.proxy_auth_lifetime_timeout
}

output "proxy_auth_timeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.proxy_auth_timeout
}

output "proxy_cipher_hardware_acceleration" {
  description = "returns a string"
  value       = data.fortios_system_global.this.proxy_cipher_hardware_acceleration
}

output "proxy_kxp_hardware_acceleration" {
  description = "returns a string"
  value       = data.fortios_system_global.this.proxy_kxp_hardware_acceleration
}

output "proxy_re_authentication_mode" {
  description = "returns a string"
  value       = data.fortios_system_global.this.proxy_re_authentication_mode
}

output "proxy_worker_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.proxy_worker_count
}

output "radius_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.radius_port
}

output "reboot_upon_config_restore" {
  description = "returns a string"
  value       = data.fortios_system_global.this.reboot_upon_config_restore
}

output "refresh" {
  description = "returns a number"
  value       = data.fortios_system_global.this.refresh
}

output "remoteauthtimeout" {
  description = "returns a number"
  value       = data.fortios_system_global.this.remoteauthtimeout
}

output "reset_sessionless_tcp" {
  description = "returns a string"
  value       = data.fortios_system_global.this.reset_sessionless_tcp
}

output "restart_time" {
  description = "returns a string"
  value       = data.fortios_system_global.this.restart_time
}

output "revision_backup_on_logout" {
  description = "returns a string"
  value       = data.fortios_system_global.this.revision_backup_on_logout
}

output "revision_image_auto_backup" {
  description = "returns a string"
  value       = data.fortios_system_global.this.revision_image_auto_backup
}

output "scanunit_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.scanunit_count
}

output "security_rating_result_submission" {
  description = "returns a string"
  value       = data.fortios_system_global.this.security_rating_result_submission
}

output "security_rating_run_on_schedule" {
  description = "returns a string"
  value       = data.fortios_system_global.this.security_rating_run_on_schedule
}

output "send_pmtu_icmp" {
  description = "returns a string"
  value       = data.fortios_system_global.this.send_pmtu_icmp
}

output "snat_route_change" {
  description = "returns a string"
  value       = data.fortios_system_global.this.snat_route_change
}

output "special_file_23_support" {
  description = "returns a string"
  value       = data.fortios_system_global.this.special_file_23_support
}

output "ssd_trim_date" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ssd_trim_date
}

output "ssd_trim_freq" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssd_trim_freq
}

output "ssd_trim_hour" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ssd_trim_hour
}

output "ssd_trim_min" {
  description = "returns a number"
  value       = data.fortios_system_global.this.ssd_trim_min
}

output "ssd_trim_weekday" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssd_trim_weekday
}

output "ssh_cbc_cipher" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssh_cbc_cipher
}

output "ssh_hmac_md5" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssh_hmac_md5
}

output "ssh_kex_sha1" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssh_kex_sha1
}

output "ssh_mac_weak" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssh_mac_weak
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssl_min_proto_version
}

output "ssl_static_key_ciphers" {
  description = "returns a string"
  value       = data.fortios_system_global.this.ssl_static_key_ciphers
}

output "sslvpn_cipher_hardware_acceleration" {
  description = "returns a string"
  value       = data.fortios_system_global.this.sslvpn_cipher_hardware_acceleration
}

output "sslvpn_ems_sn_check" {
  description = "returns a string"
  value       = data.fortios_system_global.this.sslvpn_ems_sn_check
}

output "sslvpn_kxp_hardware_acceleration" {
  description = "returns a string"
  value       = data.fortios_system_global.this.sslvpn_kxp_hardware_acceleration
}

output "sslvpn_max_worker_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.sslvpn_max_worker_count
}

output "sslvpn_plugin_version_check" {
  description = "returns a string"
  value       = data.fortios_system_global.this.sslvpn_plugin_version_check
}

output "strict_dirty_session_check" {
  description = "returns a string"
  value       = data.fortios_system_global.this.strict_dirty_session_check
}

output "strong_crypto" {
  description = "returns a string"
  value       = data.fortios_system_global.this.strong_crypto
}

output "switch_controller" {
  description = "returns a string"
  value       = data.fortios_system_global.this.switch_controller
}

output "switch_controller_reserved_network" {
  description = "returns a string"
  value       = data.fortios_system_global.this.switch_controller_reserved_network
}

output "sys_perf_log_interval" {
  description = "returns a number"
  value       = data.fortios_system_global.this.sys_perf_log_interval
}

output "tcp_halfclose_timer" {
  description = "returns a number"
  value       = data.fortios_system_global.this.tcp_halfclose_timer
}

output "tcp_halfopen_timer" {
  description = "returns a number"
  value       = data.fortios_system_global.this.tcp_halfopen_timer
}

output "tcp_option" {
  description = "returns a string"
  value       = data.fortios_system_global.this.tcp_option
}

output "tcp_timewait_timer" {
  description = "returns a number"
  value       = data.fortios_system_global.this.tcp_timewait_timer
}

output "tftp" {
  description = "returns a string"
  value       = data.fortios_system_global.this.tftp
}

output "timezone" {
  description = "returns a string"
  value       = data.fortios_system_global.this.timezone
}

output "tp_mc_skip_policy" {
  description = "returns a string"
  value       = data.fortios_system_global.this.tp_mc_skip_policy
}

output "traffic_priority" {
  description = "returns a string"
  value       = data.fortios_system_global.this.traffic_priority
}

output "traffic_priority_level" {
  description = "returns a string"
  value       = data.fortios_system_global.this.traffic_priority_level
}

output "two_factor_email_expiry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.two_factor_email_expiry
}

output "two_factor_fac_expiry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.two_factor_fac_expiry
}

output "two_factor_ftk_expiry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.two_factor_ftk_expiry
}

output "two_factor_ftm_expiry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.two_factor_ftm_expiry
}

output "two_factor_sms_expiry" {
  description = "returns a number"
  value       = data.fortios_system_global.this.two_factor_sms_expiry
}

output "udp_idle_timer" {
  description = "returns a number"
  value       = data.fortios_system_global.this.udp_idle_timer
}

output "url_filter_affinity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.url_filter_affinity
}

output "url_filter_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.url_filter_count
}

output "user_device_store_max_devices" {
  description = "returns a number"
  value       = data.fortios_system_global.this.user_device_store_max_devices
}

output "user_device_store_max_users" {
  description = "returns a number"
  value       = data.fortios_system_global.this.user_device_store_max_users
}

output "user_server_cert" {
  description = "returns a string"
  value       = data.fortios_system_global.this.user_server_cert
}

output "vdom_admin" {
  description = "returns a string"
  value       = data.fortios_system_global.this.vdom_admin
}

output "vdom_mode" {
  description = "returns a string"
  value       = data.fortios_system_global.this.vdom_mode
}

output "vip_arp_range" {
  description = "returns a string"
  value       = data.fortios_system_global.this.vip_arp_range
}

output "virtual_server_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.virtual_server_count
}

output "virtual_server_hardware_acceleration" {
  description = "returns a string"
  value       = data.fortios_system_global.this.virtual_server_hardware_acceleration
}

output "wad_affinity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.wad_affinity
}

output "wad_csvc_cs_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.wad_csvc_cs_count
}

output "wad_csvc_db_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.wad_csvc_db_count
}

output "wad_memory_change_granularity" {
  description = "returns a number"
  value       = data.fortios_system_global.this.wad_memory_change_granularity
}

output "wad_source_affinity" {
  description = "returns a string"
  value       = data.fortios_system_global.this.wad_source_affinity
}

output "wad_worker_count" {
  description = "returns a number"
  value       = data.fortios_system_global.this.wad_worker_count
}

output "wifi_ca_certificate" {
  description = "returns a string"
  value       = data.fortios_system_global.this.wifi_ca_certificate
}

output "wifi_certificate" {
  description = "returns a string"
  value       = data.fortios_system_global.this.wifi_certificate
}

output "wimax_4g_usb" {
  description = "returns a string"
  value       = data.fortios_system_global.this.wimax_4g_usb
}

output "wireless_controller" {
  description = "returns a string"
  value       = data.fortios_system_global.this.wireless_controller
}

output "wireless_controller_port" {
  description = "returns a number"
  value       = data.fortios_system_global.this.wireless_controller_port
}

output "this" {
  value = fortios_system_global.this
}
```

[top](#index)