# fortios_system_global

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
module "fortios_system_global" {
  source = "./modules/fortios/r/fortios_system_global"

  # admin_concurrent - (optional) is a type of string
  admin_concurrent = null
  # admin_console_timeout - (optional) is a type of number
  admin_console_timeout = null
  # admin_hsts_max_age - (optional) is a type of number
  admin_hsts_max_age = null
  # admin_https_pki_required - (optional) is a type of string
  admin_https_pki_required = null
  # admin_https_redirect - (optional) is a type of string
  admin_https_redirect = null
  # admin_https_ssl_versions - (optional) is a type of string
  admin_https_ssl_versions = null
  # admin_lockout_duration - (optional) is a type of number
  admin_lockout_duration = null
  # admin_lockout_threshold - (optional) is a type of number
  admin_lockout_threshold = null
  # admin_login_max - (optional) is a type of number
  admin_login_max = null
  # admin_maintainer - (optional) is a type of string
  admin_maintainer = null
  # admin_port - (optional) is a type of number
  admin_port = null
  # admin_restrict_local - (optional) is a type of string
  admin_restrict_local = null
  # admin_scp - (optional) is a type of string
  admin_scp = null
  # admin_server_cert - (optional) is a type of string
  admin_server_cert = null
  # admin_sport - (optional) is a type of number
  admin_sport = null
  # admin_ssh_grace_time - (optional) is a type of number
  admin_ssh_grace_time = null
  # admin_ssh_password - (optional) is a type of string
  admin_ssh_password = null
  # admin_ssh_port - (optional) is a type of number
  admin_ssh_port = null
  # admin_ssh_v1 - (optional) is a type of string
  admin_ssh_v1 = null
  # admin_telnet - (optional) is a type of string
  admin_telnet = null
  # admin_telnet_port - (optional) is a type of number
  admin_telnet_port = null
  # admintimeout - (optional) is a type of number
  admintimeout = null
  # alias - (optional) is a type of string
  alias = null
  # allow_traffic_redirect - (optional) is a type of string
  allow_traffic_redirect = null
  # anti_replay - (optional) is a type of string
  anti_replay = null
  # arp_max_entry - (optional) is a type of number
  arp_max_entry = null
  # asymroute - (optional) is a type of string
  asymroute = null
  # auth_cert - (optional) is a type of string
  auth_cert = null
  # auth_http_port - (optional) is a type of number
  auth_http_port = null
  # auth_https_port - (optional) is a type of number
  auth_https_port = null
  # auth_keepalive - (optional) is a type of string
  auth_keepalive = null
  # auth_session_limit - (optional) is a type of string
  auth_session_limit = null
  # auto_auth_extension_device - (optional) is a type of string
  auto_auth_extension_device = null
  # autorun_log_fsck - (optional) is a type of string
  autorun_log_fsck = null
  # av_affinity - (optional) is a type of string
  av_affinity = null
  # av_failopen - (optional) is a type of string
  av_failopen = null
  # av_failopen_session - (optional) is a type of string
  av_failopen_session = null
  # batch_cmdb - (optional) is a type of string
  batch_cmdb = null
  # block_session_timer - (optional) is a type of number
  block_session_timer = null
  # br_fdb_max_entry - (optional) is a type of number
  br_fdb_max_entry = null
  # cert_chain_max - (optional) is a type of number
  cert_chain_max = null
  # cfg_revert_timeout - (optional) is a type of number
  cfg_revert_timeout = null
  # cfg_save - (optional) is a type of string
  cfg_save = null
  # check_protocol_header - (optional) is a type of string
  check_protocol_header = null
  # check_reset_range - (optional) is a type of string
  check_reset_range = null
  # cli_audit_log - (optional) is a type of string
  cli_audit_log = null
  # cloud_communication - (optional) is a type of string
  cloud_communication = null
  # clt_cert_req - (optional) is a type of string
  clt_cert_req = null
  # compliance_check - (optional) is a type of string
  compliance_check = null
  # compliance_check_time - (optional) is a type of string
  compliance_check_time = null
  # cpu_use_threshold - (optional) is a type of number
  cpu_use_threshold = null
  # csr_ca_attribute - (optional) is a type of string
  csr_ca_attribute = null
  # daily_restart - (optional) is a type of string
  daily_restart = null
  # default_service_source_port - (optional) is a type of string
  default_service_source_port = null
  # device_identification_active_scan_delay - (optional) is a type of number
  device_identification_active_scan_delay = null
  # device_idle_timeout - (optional) is a type of number
  device_idle_timeout = null
  # dh_params - (optional) is a type of string
  dh_params = null
  # dnsproxy_worker_count - (optional) is a type of number
  dnsproxy_worker_count = null
  # dst - (optional) is a type of string
  dst = null
  # endpoint_control_fds_access - (optional) is a type of string
  endpoint_control_fds_access = null
  # endpoint_control_portal_port - (optional) is a type of number
  endpoint_control_portal_port = null
  # failtime - (optional) is a type of number
  failtime = null
  # faz_disk_buffer_size - (optional) is a type of number
  faz_disk_buffer_size = null
  # fds_statistics - (optional) is a type of string
  fds_statistics = null
  # fds_statistics_period - (optional) is a type of number
  fds_statistics_period = null
  # fec_port - (optional) is a type of number
  fec_port = null
  # fgd_alert_subscription - (optional) is a type of string
  fgd_alert_subscription = null
  # fortiextender - (optional) is a type of string
  fortiextender = null
  # fortiextender_data_port - (optional) is a type of number
  fortiextender_data_port = null
  # fortiextender_vlan_mode - (optional) is a type of string
  fortiextender_vlan_mode = null
  # fortiipam_integration - (optional) is a type of string
  fortiipam_integration = null
  # fortiservice_port - (optional) is a type of number
  fortiservice_port = null
  # fortitoken_cloud - (optional) is a type of string
  fortitoken_cloud = null
  # gui_allow_default_hostname - (optional) is a type of string
  gui_allow_default_hostname = null
  # gui_certificates - (optional) is a type of string
  gui_certificates = null
  # gui_custom_language - (optional) is a type of string
  gui_custom_language = null
  # gui_date_format - (optional) is a type of string
  gui_date_format = null
  # gui_date_time_source - (optional) is a type of string
  gui_date_time_source = null
  # gui_device_latitude - (optional) is a type of string
  gui_device_latitude = null
  # gui_device_longitude - (optional) is a type of string
  gui_device_longitude = null
  # gui_display_hostname - (optional) is a type of string
  gui_display_hostname = null
  # gui_firmware_upgrade_setup_warning - (optional) is a type of string
  gui_firmware_upgrade_setup_warning = null
  # gui_firmware_upgrade_warning - (optional) is a type of string
  gui_firmware_upgrade_warning = null
  # gui_forticare_registration_setup_warning - (optional) is a type of string
  gui_forticare_registration_setup_warning = null
  # gui_fortigate_cloud_sandbox - (optional) is a type of string
  gui_fortigate_cloud_sandbox = null
  # gui_fortisandbox_cloud - (optional) is a type of string
  gui_fortisandbox_cloud = null
  # gui_ipv6 - (optional) is a type of string
  gui_ipv6 = null
  # gui_lines_per_page - (optional) is a type of number
  gui_lines_per_page = null
  # gui_theme - (optional) is a type of string
  gui_theme = null
  # gui_wireless_opensecurity - (optional) is a type of string
  gui_wireless_opensecurity = null
  # honor_df - (optional) is a type of string
  honor_df = null
  # hostname - (optional) is a type of string
  hostname = null
  # igmp_state_limit - (optional) is a type of number
  igmp_state_limit = null
  # ike_embryonic_limit - (optional) is a type of number
  ike_embryonic_limit = null
  # interval - (optional) is a type of number
  interval = null
  # ip_src_port_range - (optional) is a type of string
  ip_src_port_range = null
  # ips_affinity - (optional) is a type of string
  ips_affinity = null
  # ipsec_asic_offload - (optional) is a type of string
  ipsec_asic_offload = null
  # ipsec_hmac_offload - (optional) is a type of string
  ipsec_hmac_offload = null
  # ipsec_soft_dec_async - (optional) is a type of string
  ipsec_soft_dec_async = null
  # ipv6_accept_dad - (optional) is a type of number
  ipv6_accept_dad = null
  # ipv6_allow_anycast_probe - (optional) is a type of string
  ipv6_allow_anycast_probe = null
  # ipv6_allow_traffic_redirect - (optional) is a type of string
  ipv6_allow_traffic_redirect = null
  # irq_time_accounting - (optional) is a type of string
  irq_time_accounting = null
  # language - (optional) is a type of string
  language = null
  # ldapconntimeout - (optional) is a type of number
  ldapconntimeout = null
  # lldp_reception - (optional) is a type of string
  lldp_reception = null
  # lldp_transmission - (optional) is a type of string
  lldp_transmission = null
  # log_ssl_connection - (optional) is a type of string
  log_ssl_connection = null
  # log_uuid_address - (optional) is a type of string
  log_uuid_address = null
  # log_uuid_policy - (optional) is a type of string
  log_uuid_policy = null
  # login_timestamp - (optional) is a type of string
  login_timestamp = null
  # long_vdom_name - (optional) is a type of string
  long_vdom_name = null
  # management_vdom - (optional) is a type of string
  management_vdom = null
  # max_dlpstat_memory - (optional) is a type of number
  max_dlpstat_memory = null
  # max_route_cache_size - (optional) is a type of number
  max_route_cache_size = null
  # mc_ttl_notchange - (optional) is a type of string
  mc_ttl_notchange = null
  # memory_use_threshold_extreme - (optional) is a type of number
  memory_use_threshold_extreme = null
  # memory_use_threshold_green - (optional) is a type of number
  memory_use_threshold_green = null
  # memory_use_threshold_red - (optional) is a type of number
  memory_use_threshold_red = null
  # miglog_affinity - (optional) is a type of string
  miglog_affinity = null
  # miglogd_children - (optional) is a type of number
  miglogd_children = null
  # multi_factor_authentication - (optional) is a type of string
  multi_factor_authentication = null
  # multicast_forward - (optional) is a type of string
  multicast_forward = null
  # ndp_max_entry - (optional) is a type of number
  ndp_max_entry = null
  # per_user_bal - (optional) is a type of string
  per_user_bal = null
  # per_user_bwl - (optional) is a type of string
  per_user_bwl = null
  # policy_auth_concurrent - (optional) is a type of number
  policy_auth_concurrent = null
  # post_login_banner - (optional) is a type of string
  post_login_banner = null
  # pre_login_banner - (optional) is a type of string
  pre_login_banner = null
  # private_data_encryption - (optional) is a type of string
  private_data_encryption = null
  # proxy_auth_lifetime - (optional) is a type of string
  proxy_auth_lifetime = null
  # proxy_auth_lifetime_timeout - (optional) is a type of number
  proxy_auth_lifetime_timeout = null
  # proxy_auth_timeout - (optional) is a type of number
  proxy_auth_timeout = null
  # proxy_cipher_hardware_acceleration - (optional) is a type of string
  proxy_cipher_hardware_acceleration = null
  # proxy_kxp_hardware_acceleration - (optional) is a type of string
  proxy_kxp_hardware_acceleration = null
  # proxy_re_authentication_mode - (optional) is a type of string
  proxy_re_authentication_mode = null
  # proxy_worker_count - (optional) is a type of number
  proxy_worker_count = null
  # radius_port - (optional) is a type of number
  radius_port = null
  # reboot_upon_config_restore - (optional) is a type of string
  reboot_upon_config_restore = null
  # refresh - (optional) is a type of number
  refresh = null
  # remoteauthtimeout - (optional) is a type of number
  remoteauthtimeout = null
  # reset_sessionless_tcp - (optional) is a type of string
  reset_sessionless_tcp = null
  # restart_time - (optional) is a type of string
  restart_time = null
  # revision_backup_on_logout - (optional) is a type of string
  revision_backup_on_logout = null
  # revision_image_auto_backup - (optional) is a type of string
  revision_image_auto_backup = null
  # scanunit_count - (optional) is a type of number
  scanunit_count = null
  # security_rating_result_submission - (optional) is a type of string
  security_rating_result_submission = null
  # security_rating_run_on_schedule - (optional) is a type of string
  security_rating_run_on_schedule = null
  # send_pmtu_icmp - (optional) is a type of string
  send_pmtu_icmp = null
  # snat_route_change - (optional) is a type of string
  snat_route_change = null
  # special_file_23_support - (optional) is a type of string
  special_file_23_support = null
  # ssd_trim_date - (optional) is a type of number
  ssd_trim_date = null
  # ssd_trim_freq - (optional) is a type of string
  ssd_trim_freq = null
  # ssd_trim_hour - (optional) is a type of number
  ssd_trim_hour = null
  # ssd_trim_min - (optional) is a type of number
  ssd_trim_min = null
  # ssd_trim_weekday - (optional) is a type of string
  ssd_trim_weekday = null
  # ssh_cbc_cipher - (optional) is a type of string
  ssh_cbc_cipher = null
  # ssh_hmac_md5 - (optional) is a type of string
  ssh_hmac_md5 = null
  # ssh_kex_sha1 - (optional) is a type of string
  ssh_kex_sha1 = null
  # ssh_mac_weak - (optional) is a type of string
  ssh_mac_weak = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # ssl_static_key_ciphers - (optional) is a type of string
  ssl_static_key_ciphers = null
  # sslvpn_cipher_hardware_acceleration - (optional) is a type of string
  sslvpn_cipher_hardware_acceleration = null
  # sslvpn_ems_sn_check - (optional) is a type of string
  sslvpn_ems_sn_check = null
  # sslvpn_kxp_hardware_acceleration - (optional) is a type of string
  sslvpn_kxp_hardware_acceleration = null
  # sslvpn_max_worker_count - (optional) is a type of number
  sslvpn_max_worker_count = null
  # sslvpn_plugin_version_check - (optional) is a type of string
  sslvpn_plugin_version_check = null
  # strict_dirty_session_check - (optional) is a type of string
  strict_dirty_session_check = null
  # strong_crypto - (optional) is a type of string
  strong_crypto = null
  # switch_controller - (optional) is a type of string
  switch_controller = null
  # switch_controller_reserved_network - (optional) is a type of string
  switch_controller_reserved_network = null
  # sys_perf_log_interval - (optional) is a type of number
  sys_perf_log_interval = null
  # tcp_halfclose_timer - (optional) is a type of number
  tcp_halfclose_timer = null
  # tcp_halfopen_timer - (optional) is a type of number
  tcp_halfopen_timer = null
  # tcp_option - (optional) is a type of string
  tcp_option = null
  # tcp_timewait_timer - (optional) is a type of number
  tcp_timewait_timer = null
  # tftp - (optional) is a type of string
  tftp = null
  # timezone - (optional) is a type of string
  timezone = null
  # tp_mc_skip_policy - (optional) is a type of string
  tp_mc_skip_policy = null
  # traffic_priority - (optional) is a type of string
  traffic_priority = null
  # traffic_priority_level - (optional) is a type of string
  traffic_priority_level = null
  # two_factor_email_expiry - (optional) is a type of number
  two_factor_email_expiry = null
  # two_factor_fac_expiry - (optional) is a type of number
  two_factor_fac_expiry = null
  # two_factor_ftk_expiry - (optional) is a type of number
  two_factor_ftk_expiry = null
  # two_factor_ftm_expiry - (optional) is a type of number
  two_factor_ftm_expiry = null
  # two_factor_sms_expiry - (optional) is a type of number
  two_factor_sms_expiry = null
  # udp_idle_timer - (optional) is a type of number
  udp_idle_timer = null
  # url_filter_affinity - (optional) is a type of string
  url_filter_affinity = null
  # url_filter_count - (optional) is a type of number
  url_filter_count = null
  # user_device_store_max_devices - (optional) is a type of number
  user_device_store_max_devices = null
  # user_device_store_max_users - (optional) is a type of number
  user_device_store_max_users = null
  # user_server_cert - (optional) is a type of string
  user_server_cert = null
  # vdom_admin - (optional) is a type of string
  vdom_admin = null
  # vdom_mode - (optional) is a type of string
  vdom_mode = null
  # vip_arp_range - (optional) is a type of string
  vip_arp_range = null
  # virtual_server_count - (optional) is a type of number
  virtual_server_count = null
  # virtual_server_hardware_acceleration - (optional) is a type of string
  virtual_server_hardware_acceleration = null
  # wad_affinity - (optional) is a type of string
  wad_affinity = null
  # wad_csvc_cs_count - (optional) is a type of number
  wad_csvc_cs_count = null
  # wad_csvc_db_count - (optional) is a type of number
  wad_csvc_db_count = null
  # wad_memory_change_granularity - (optional) is a type of number
  wad_memory_change_granularity = null
  # wad_source_affinity - (optional) is a type of string
  wad_source_affinity = null
  # wad_worker_count - (optional) is a type of number
  wad_worker_count = null
  # wifi_ca_certificate - (optional) is a type of string
  wifi_ca_certificate = null
  # wifi_certificate - (optional) is a type of string
  wifi_certificate = null
  # wimax_4g_usb - (optional) is a type of string
  wimax_4g_usb = null
  # wireless_controller - (optional) is a type of string
  wireless_controller = null
  # wireless_controller_port - (optional) is a type of number
  wireless_controller_port = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_concurrent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_console_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_hsts_max_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_https_pki_required" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_https_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_https_ssl_versions" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_lockout_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_lockout_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_login_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_maintainer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_restrict_local" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_scp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_server_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_sport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_ssh_grace_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_ssh_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_ssh_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admin_ssh_v1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_telnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_telnet_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "admintimeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_traffic_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anti_replay" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_max_entry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "asymroute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_http_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_https_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_keepalive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_session_limit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_auth_extension_device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autorun_log_fsck" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_failopen" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_failopen_session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "batch_cmdb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_session_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "br_fdb_max_entry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cert_chain_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cfg_revert_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cfg_save" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_protocol_header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_reset_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cli_audit_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_communication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clt_cert_req" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compliance_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compliance_check_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_use_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "csr_ca_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "daily_restart" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_service_source_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_identification_active_scan_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dh_params" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnsproxy_worker_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_control_fds_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_control_portal_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failtime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "faz_disk_buffer_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fds_statistics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fds_statistics_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fec_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fgd_alert_subscription" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiextender" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiextender_data_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fortiextender_vlan_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiipam_integration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiservice_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fortitoken_cloud" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_allow_default_hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_certificates" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_custom_language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_date_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_date_time_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_device_latitude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_device_longitude" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_display_hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_firmware_upgrade_setup_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_firmware_upgrade_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_forticare_registration_setup_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_fortigate_cloud_sandbox" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_fortisandbox_cloud" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_lines_per_page" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gui_theme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gui_wireless_opensecurity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "honor_df" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "igmp_state_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ike_embryonic_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_src_port_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_asic_offload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_hmac_offload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_soft_dec_async" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_accept_dad" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_allow_anycast_probe" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_allow_traffic_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "irq_time_accounting" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldapconntimeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lldp_reception" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp_transmission" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_ssl_connection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_uuid_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_uuid_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_timestamp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "long_vdom_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_dlpstat_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_route_cache_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mc_ttl_notchange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_use_threshold_extreme" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "memory_use_threshold_green" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "memory_use_threshold_red" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "miglog_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "miglogd_children" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "multi_factor_authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ndp_max_entry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "per_user_bal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_user_bwl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_auth_concurrent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "post_login_banner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pre_login_banner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_data_encryption" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_auth_lifetime" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_auth_lifetime_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy_auth_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy_cipher_hardware_acceleration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_kxp_hardware_acceleration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_re_authentication_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_worker_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "radius_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reboot_upon_config_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remoteauthtimeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_sessionless_tcp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restart_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "revision_backup_on_logout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "revision_image_auto_backup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scanunit_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_rating_result_submission" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_rating_run_on_schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "send_pmtu_icmp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snat_route_change" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "special_file_23_support" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssd_trim_date" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssd_trim_freq" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssd_trim_hour" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssd_trim_min" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssd_trim_weekday" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_cbc_cipher" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_hmac_md5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_kex_sha1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_mac_weak" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_static_key_ciphers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_cipher_hardware_acceleration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_ems_sn_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_kxp_hardware_acceleration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_max_worker_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sslvpn_plugin_version_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_dirty_session_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strong_crypto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_controller_reserved_network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sys_perf_log_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_halfclose_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_halfopen_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_timewait_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tftp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tp_mc_skip_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_priority_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor_email_expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "two_factor_fac_expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "two_factor_ftk_expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "two_factor_ftm_expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "two_factor_sms_expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "udp_idle_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url_filter_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_filter_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_device_store_max_devices" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_device_store_max_users" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_server_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom_admin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vip_arp_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_server_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "virtual_server_hardware_acceleration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wad_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wad_csvc_cs_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wad_csvc_db_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wad_memory_change_granularity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wad_source_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wad_worker_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wifi_ca_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wifi_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wimax_4g_usb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wireless_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wireless_controller_port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_global" "this" {
  # admin_concurrent - (optional) is a type of string
  admin_concurrent = var.admin_concurrent
  # admin_console_timeout - (optional) is a type of number
  admin_console_timeout = var.admin_console_timeout
  # admin_hsts_max_age - (optional) is a type of number
  admin_hsts_max_age = var.admin_hsts_max_age
  # admin_https_pki_required - (optional) is a type of string
  admin_https_pki_required = var.admin_https_pki_required
  # admin_https_redirect - (optional) is a type of string
  admin_https_redirect = var.admin_https_redirect
  # admin_https_ssl_versions - (optional) is a type of string
  admin_https_ssl_versions = var.admin_https_ssl_versions
  # admin_lockout_duration - (optional) is a type of number
  admin_lockout_duration = var.admin_lockout_duration
  # admin_lockout_threshold - (optional) is a type of number
  admin_lockout_threshold = var.admin_lockout_threshold
  # admin_login_max - (optional) is a type of number
  admin_login_max = var.admin_login_max
  # admin_maintainer - (optional) is a type of string
  admin_maintainer = var.admin_maintainer
  # admin_port - (optional) is a type of number
  admin_port = var.admin_port
  # admin_restrict_local - (optional) is a type of string
  admin_restrict_local = var.admin_restrict_local
  # admin_scp - (optional) is a type of string
  admin_scp = var.admin_scp
  # admin_server_cert - (optional) is a type of string
  admin_server_cert = var.admin_server_cert
  # admin_sport - (optional) is a type of number
  admin_sport = var.admin_sport
  # admin_ssh_grace_time - (optional) is a type of number
  admin_ssh_grace_time = var.admin_ssh_grace_time
  # admin_ssh_password - (optional) is a type of string
  admin_ssh_password = var.admin_ssh_password
  # admin_ssh_port - (optional) is a type of number
  admin_ssh_port = var.admin_ssh_port
  # admin_ssh_v1 - (optional) is a type of string
  admin_ssh_v1 = var.admin_ssh_v1
  # admin_telnet - (optional) is a type of string
  admin_telnet = var.admin_telnet
  # admin_telnet_port - (optional) is a type of number
  admin_telnet_port = var.admin_telnet_port
  # admintimeout - (optional) is a type of number
  admintimeout = var.admintimeout
  # alias - (optional) is a type of string
  alias = var.alias
  # allow_traffic_redirect - (optional) is a type of string
  allow_traffic_redirect = var.allow_traffic_redirect
  # anti_replay - (optional) is a type of string
  anti_replay = var.anti_replay
  # arp_max_entry - (optional) is a type of number
  arp_max_entry = var.arp_max_entry
  # asymroute - (optional) is a type of string
  asymroute = var.asymroute
  # auth_cert - (optional) is a type of string
  auth_cert = var.auth_cert
  # auth_http_port - (optional) is a type of number
  auth_http_port = var.auth_http_port
  # auth_https_port - (optional) is a type of number
  auth_https_port = var.auth_https_port
  # auth_keepalive - (optional) is a type of string
  auth_keepalive = var.auth_keepalive
  # auth_session_limit - (optional) is a type of string
  auth_session_limit = var.auth_session_limit
  # auto_auth_extension_device - (optional) is a type of string
  auto_auth_extension_device = var.auto_auth_extension_device
  # autorun_log_fsck - (optional) is a type of string
  autorun_log_fsck = var.autorun_log_fsck
  # av_affinity - (optional) is a type of string
  av_affinity = var.av_affinity
  # av_failopen - (optional) is a type of string
  av_failopen = var.av_failopen
  # av_failopen_session - (optional) is a type of string
  av_failopen_session = var.av_failopen_session
  # batch_cmdb - (optional) is a type of string
  batch_cmdb = var.batch_cmdb
  # block_session_timer - (optional) is a type of number
  block_session_timer = var.block_session_timer
  # br_fdb_max_entry - (optional) is a type of number
  br_fdb_max_entry = var.br_fdb_max_entry
  # cert_chain_max - (optional) is a type of number
  cert_chain_max = var.cert_chain_max
  # cfg_revert_timeout - (optional) is a type of number
  cfg_revert_timeout = var.cfg_revert_timeout
  # cfg_save - (optional) is a type of string
  cfg_save = var.cfg_save
  # check_protocol_header - (optional) is a type of string
  check_protocol_header = var.check_protocol_header
  # check_reset_range - (optional) is a type of string
  check_reset_range = var.check_reset_range
  # cli_audit_log - (optional) is a type of string
  cli_audit_log = var.cli_audit_log
  # cloud_communication - (optional) is a type of string
  cloud_communication = var.cloud_communication
  # clt_cert_req - (optional) is a type of string
  clt_cert_req = var.clt_cert_req
  # compliance_check - (optional) is a type of string
  compliance_check = var.compliance_check
  # compliance_check_time - (optional) is a type of string
  compliance_check_time = var.compliance_check_time
  # cpu_use_threshold - (optional) is a type of number
  cpu_use_threshold = var.cpu_use_threshold
  # csr_ca_attribute - (optional) is a type of string
  csr_ca_attribute = var.csr_ca_attribute
  # daily_restart - (optional) is a type of string
  daily_restart = var.daily_restart
  # default_service_source_port - (optional) is a type of string
  default_service_source_port = var.default_service_source_port
  # device_identification_active_scan_delay - (optional) is a type of number
  device_identification_active_scan_delay = var.device_identification_active_scan_delay
  # device_idle_timeout - (optional) is a type of number
  device_idle_timeout = var.device_idle_timeout
  # dh_params - (optional) is a type of string
  dh_params = var.dh_params
  # dnsproxy_worker_count - (optional) is a type of number
  dnsproxy_worker_count = var.dnsproxy_worker_count
  # dst - (optional) is a type of string
  dst = var.dst
  # endpoint_control_fds_access - (optional) is a type of string
  endpoint_control_fds_access = var.endpoint_control_fds_access
  # endpoint_control_portal_port - (optional) is a type of number
  endpoint_control_portal_port = var.endpoint_control_portal_port
  # failtime - (optional) is a type of number
  failtime = var.failtime
  # faz_disk_buffer_size - (optional) is a type of number
  faz_disk_buffer_size = var.faz_disk_buffer_size
  # fds_statistics - (optional) is a type of string
  fds_statistics = var.fds_statistics
  # fds_statistics_period - (optional) is a type of number
  fds_statistics_period = var.fds_statistics_period
  # fec_port - (optional) is a type of number
  fec_port = var.fec_port
  # fgd_alert_subscription - (optional) is a type of string
  fgd_alert_subscription = var.fgd_alert_subscription
  # fortiextender - (optional) is a type of string
  fortiextender = var.fortiextender
  # fortiextender_data_port - (optional) is a type of number
  fortiextender_data_port = var.fortiextender_data_port
  # fortiextender_vlan_mode - (optional) is a type of string
  fortiextender_vlan_mode = var.fortiextender_vlan_mode
  # fortiipam_integration - (optional) is a type of string
  fortiipam_integration = var.fortiipam_integration
  # fortiservice_port - (optional) is a type of number
  fortiservice_port = var.fortiservice_port
  # fortitoken_cloud - (optional) is a type of string
  fortitoken_cloud = var.fortitoken_cloud
  # gui_allow_default_hostname - (optional) is a type of string
  gui_allow_default_hostname = var.gui_allow_default_hostname
  # gui_certificates - (optional) is a type of string
  gui_certificates = var.gui_certificates
  # gui_custom_language - (optional) is a type of string
  gui_custom_language = var.gui_custom_language
  # gui_date_format - (optional) is a type of string
  gui_date_format = var.gui_date_format
  # gui_date_time_source - (optional) is a type of string
  gui_date_time_source = var.gui_date_time_source
  # gui_device_latitude - (optional) is a type of string
  gui_device_latitude = var.gui_device_latitude
  # gui_device_longitude - (optional) is a type of string
  gui_device_longitude = var.gui_device_longitude
  # gui_display_hostname - (optional) is a type of string
  gui_display_hostname = var.gui_display_hostname
  # gui_firmware_upgrade_setup_warning - (optional) is a type of string
  gui_firmware_upgrade_setup_warning = var.gui_firmware_upgrade_setup_warning
  # gui_firmware_upgrade_warning - (optional) is a type of string
  gui_firmware_upgrade_warning = var.gui_firmware_upgrade_warning
  # gui_forticare_registration_setup_warning - (optional) is a type of string
  gui_forticare_registration_setup_warning = var.gui_forticare_registration_setup_warning
  # gui_fortigate_cloud_sandbox - (optional) is a type of string
  gui_fortigate_cloud_sandbox = var.gui_fortigate_cloud_sandbox
  # gui_fortisandbox_cloud - (optional) is a type of string
  gui_fortisandbox_cloud = var.gui_fortisandbox_cloud
  # gui_ipv6 - (optional) is a type of string
  gui_ipv6 = var.gui_ipv6
  # gui_lines_per_page - (optional) is a type of number
  gui_lines_per_page = var.gui_lines_per_page
  # gui_theme - (optional) is a type of string
  gui_theme = var.gui_theme
  # gui_wireless_opensecurity - (optional) is a type of string
  gui_wireless_opensecurity = var.gui_wireless_opensecurity
  # honor_df - (optional) is a type of string
  honor_df = var.honor_df
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # igmp_state_limit - (optional) is a type of number
  igmp_state_limit = var.igmp_state_limit
  # ike_embryonic_limit - (optional) is a type of number
  ike_embryonic_limit = var.ike_embryonic_limit
  # interval - (optional) is a type of number
  interval = var.interval
  # ip_src_port_range - (optional) is a type of string
  ip_src_port_range = var.ip_src_port_range
  # ips_affinity - (optional) is a type of string
  ips_affinity = var.ips_affinity
  # ipsec_asic_offload - (optional) is a type of string
  ipsec_asic_offload = var.ipsec_asic_offload
  # ipsec_hmac_offload - (optional) is a type of string
  ipsec_hmac_offload = var.ipsec_hmac_offload
  # ipsec_soft_dec_async - (optional) is a type of string
  ipsec_soft_dec_async = var.ipsec_soft_dec_async
  # ipv6_accept_dad - (optional) is a type of number
  ipv6_accept_dad = var.ipv6_accept_dad
  # ipv6_allow_anycast_probe - (optional) is a type of string
  ipv6_allow_anycast_probe = var.ipv6_allow_anycast_probe
  # ipv6_allow_traffic_redirect - (optional) is a type of string
  ipv6_allow_traffic_redirect = var.ipv6_allow_traffic_redirect
  # irq_time_accounting - (optional) is a type of string
  irq_time_accounting = var.irq_time_accounting
  # language - (optional) is a type of string
  language = var.language
  # ldapconntimeout - (optional) is a type of number
  ldapconntimeout = var.ldapconntimeout
  # lldp_reception - (optional) is a type of string
  lldp_reception = var.lldp_reception
  # lldp_transmission - (optional) is a type of string
  lldp_transmission = var.lldp_transmission
  # log_ssl_connection - (optional) is a type of string
  log_ssl_connection = var.log_ssl_connection
  # log_uuid_address - (optional) is a type of string
  log_uuid_address = var.log_uuid_address
  # log_uuid_policy - (optional) is a type of string
  log_uuid_policy = var.log_uuid_policy
  # login_timestamp - (optional) is a type of string
  login_timestamp = var.login_timestamp
  # long_vdom_name - (optional) is a type of string
  long_vdom_name = var.long_vdom_name
  # management_vdom - (optional) is a type of string
  management_vdom = var.management_vdom
  # max_dlpstat_memory - (optional) is a type of number
  max_dlpstat_memory = var.max_dlpstat_memory
  # max_route_cache_size - (optional) is a type of number
  max_route_cache_size = var.max_route_cache_size
  # mc_ttl_notchange - (optional) is a type of string
  mc_ttl_notchange = var.mc_ttl_notchange
  # memory_use_threshold_extreme - (optional) is a type of number
  memory_use_threshold_extreme = var.memory_use_threshold_extreme
  # memory_use_threshold_green - (optional) is a type of number
  memory_use_threshold_green = var.memory_use_threshold_green
  # memory_use_threshold_red - (optional) is a type of number
  memory_use_threshold_red = var.memory_use_threshold_red
  # miglog_affinity - (optional) is a type of string
  miglog_affinity = var.miglog_affinity
  # miglogd_children - (optional) is a type of number
  miglogd_children = var.miglogd_children
  # multi_factor_authentication - (optional) is a type of string
  multi_factor_authentication = var.multi_factor_authentication
  # multicast_forward - (optional) is a type of string
  multicast_forward = var.multicast_forward
  # ndp_max_entry - (optional) is a type of number
  ndp_max_entry = var.ndp_max_entry
  # per_user_bal - (optional) is a type of string
  per_user_bal = var.per_user_bal
  # per_user_bwl - (optional) is a type of string
  per_user_bwl = var.per_user_bwl
  # policy_auth_concurrent - (optional) is a type of number
  policy_auth_concurrent = var.policy_auth_concurrent
  # post_login_banner - (optional) is a type of string
  post_login_banner = var.post_login_banner
  # pre_login_banner - (optional) is a type of string
  pre_login_banner = var.pre_login_banner
  # private_data_encryption - (optional) is a type of string
  private_data_encryption = var.private_data_encryption
  # proxy_auth_lifetime - (optional) is a type of string
  proxy_auth_lifetime = var.proxy_auth_lifetime
  # proxy_auth_lifetime_timeout - (optional) is a type of number
  proxy_auth_lifetime_timeout = var.proxy_auth_lifetime_timeout
  # proxy_auth_timeout - (optional) is a type of number
  proxy_auth_timeout = var.proxy_auth_timeout
  # proxy_cipher_hardware_acceleration - (optional) is a type of string
  proxy_cipher_hardware_acceleration = var.proxy_cipher_hardware_acceleration
  # proxy_kxp_hardware_acceleration - (optional) is a type of string
  proxy_kxp_hardware_acceleration = var.proxy_kxp_hardware_acceleration
  # proxy_re_authentication_mode - (optional) is a type of string
  proxy_re_authentication_mode = var.proxy_re_authentication_mode
  # proxy_worker_count - (optional) is a type of number
  proxy_worker_count = var.proxy_worker_count
  # radius_port - (optional) is a type of number
  radius_port = var.radius_port
  # reboot_upon_config_restore - (optional) is a type of string
  reboot_upon_config_restore = var.reboot_upon_config_restore
  # refresh - (optional) is a type of number
  refresh = var.refresh
  # remoteauthtimeout - (optional) is a type of number
  remoteauthtimeout = var.remoteauthtimeout
  # reset_sessionless_tcp - (optional) is a type of string
  reset_sessionless_tcp = var.reset_sessionless_tcp
  # restart_time - (optional) is a type of string
  restart_time = var.restart_time
  # revision_backup_on_logout - (optional) is a type of string
  revision_backup_on_logout = var.revision_backup_on_logout
  # revision_image_auto_backup - (optional) is a type of string
  revision_image_auto_backup = var.revision_image_auto_backup
  # scanunit_count - (optional) is a type of number
  scanunit_count = var.scanunit_count
  # security_rating_result_submission - (optional) is a type of string
  security_rating_result_submission = var.security_rating_result_submission
  # security_rating_run_on_schedule - (optional) is a type of string
  security_rating_run_on_schedule = var.security_rating_run_on_schedule
  # send_pmtu_icmp - (optional) is a type of string
  send_pmtu_icmp = var.send_pmtu_icmp
  # snat_route_change - (optional) is a type of string
  snat_route_change = var.snat_route_change
  # special_file_23_support - (optional) is a type of string
  special_file_23_support = var.special_file_23_support
  # ssd_trim_date - (optional) is a type of number
  ssd_trim_date = var.ssd_trim_date
  # ssd_trim_freq - (optional) is a type of string
  ssd_trim_freq = var.ssd_trim_freq
  # ssd_trim_hour - (optional) is a type of number
  ssd_trim_hour = var.ssd_trim_hour
  # ssd_trim_min - (optional) is a type of number
  ssd_trim_min = var.ssd_trim_min
  # ssd_trim_weekday - (optional) is a type of string
  ssd_trim_weekday = var.ssd_trim_weekday
  # ssh_cbc_cipher - (optional) is a type of string
  ssh_cbc_cipher = var.ssh_cbc_cipher
  # ssh_hmac_md5 - (optional) is a type of string
  ssh_hmac_md5 = var.ssh_hmac_md5
  # ssh_kex_sha1 - (optional) is a type of string
  ssh_kex_sha1 = var.ssh_kex_sha1
  # ssh_mac_weak - (optional) is a type of string
  ssh_mac_weak = var.ssh_mac_weak
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = var.ssl_min_proto_version
  # ssl_static_key_ciphers - (optional) is a type of string
  ssl_static_key_ciphers = var.ssl_static_key_ciphers
  # sslvpn_cipher_hardware_acceleration - (optional) is a type of string
  sslvpn_cipher_hardware_acceleration = var.sslvpn_cipher_hardware_acceleration
  # sslvpn_ems_sn_check - (optional) is a type of string
  sslvpn_ems_sn_check = var.sslvpn_ems_sn_check
  # sslvpn_kxp_hardware_acceleration - (optional) is a type of string
  sslvpn_kxp_hardware_acceleration = var.sslvpn_kxp_hardware_acceleration
  # sslvpn_max_worker_count - (optional) is a type of number
  sslvpn_max_worker_count = var.sslvpn_max_worker_count
  # sslvpn_plugin_version_check - (optional) is a type of string
  sslvpn_plugin_version_check = var.sslvpn_plugin_version_check
  # strict_dirty_session_check - (optional) is a type of string
  strict_dirty_session_check = var.strict_dirty_session_check
  # strong_crypto - (optional) is a type of string
  strong_crypto = var.strong_crypto
  # switch_controller - (optional) is a type of string
  switch_controller = var.switch_controller
  # switch_controller_reserved_network - (optional) is a type of string
  switch_controller_reserved_network = var.switch_controller_reserved_network
  # sys_perf_log_interval - (optional) is a type of number
  sys_perf_log_interval = var.sys_perf_log_interval
  # tcp_halfclose_timer - (optional) is a type of number
  tcp_halfclose_timer = var.tcp_halfclose_timer
  # tcp_halfopen_timer - (optional) is a type of number
  tcp_halfopen_timer = var.tcp_halfopen_timer
  # tcp_option - (optional) is a type of string
  tcp_option = var.tcp_option
  # tcp_timewait_timer - (optional) is a type of number
  tcp_timewait_timer = var.tcp_timewait_timer
  # tftp - (optional) is a type of string
  tftp = var.tftp
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # tp_mc_skip_policy - (optional) is a type of string
  tp_mc_skip_policy = var.tp_mc_skip_policy
  # traffic_priority - (optional) is a type of string
  traffic_priority = var.traffic_priority
  # traffic_priority_level - (optional) is a type of string
  traffic_priority_level = var.traffic_priority_level
  # two_factor_email_expiry - (optional) is a type of number
  two_factor_email_expiry = var.two_factor_email_expiry
  # two_factor_fac_expiry - (optional) is a type of number
  two_factor_fac_expiry = var.two_factor_fac_expiry
  # two_factor_ftk_expiry - (optional) is a type of number
  two_factor_ftk_expiry = var.two_factor_ftk_expiry
  # two_factor_ftm_expiry - (optional) is a type of number
  two_factor_ftm_expiry = var.two_factor_ftm_expiry
  # two_factor_sms_expiry - (optional) is a type of number
  two_factor_sms_expiry = var.two_factor_sms_expiry
  # udp_idle_timer - (optional) is a type of number
  udp_idle_timer = var.udp_idle_timer
  # url_filter_affinity - (optional) is a type of string
  url_filter_affinity = var.url_filter_affinity
  # url_filter_count - (optional) is a type of number
  url_filter_count = var.url_filter_count
  # user_device_store_max_devices - (optional) is a type of number
  user_device_store_max_devices = var.user_device_store_max_devices
  # user_device_store_max_users - (optional) is a type of number
  user_device_store_max_users = var.user_device_store_max_users
  # user_server_cert - (optional) is a type of string
  user_server_cert = var.user_server_cert
  # vdom_admin - (optional) is a type of string
  vdom_admin = var.vdom_admin
  # vdom_mode - (optional) is a type of string
  vdom_mode = var.vdom_mode
  # vip_arp_range - (optional) is a type of string
  vip_arp_range = var.vip_arp_range
  # virtual_server_count - (optional) is a type of number
  virtual_server_count = var.virtual_server_count
  # virtual_server_hardware_acceleration - (optional) is a type of string
  virtual_server_hardware_acceleration = var.virtual_server_hardware_acceleration
  # wad_affinity - (optional) is a type of string
  wad_affinity = var.wad_affinity
  # wad_csvc_cs_count - (optional) is a type of number
  wad_csvc_cs_count = var.wad_csvc_cs_count
  # wad_csvc_db_count - (optional) is a type of number
  wad_csvc_db_count = var.wad_csvc_db_count
  # wad_memory_change_granularity - (optional) is a type of number
  wad_memory_change_granularity = var.wad_memory_change_granularity
  # wad_source_affinity - (optional) is a type of string
  wad_source_affinity = var.wad_source_affinity
  # wad_worker_count - (optional) is a type of number
  wad_worker_count = var.wad_worker_count
  # wifi_ca_certificate - (optional) is a type of string
  wifi_ca_certificate = var.wifi_ca_certificate
  # wifi_certificate - (optional) is a type of string
  wifi_certificate = var.wifi_certificate
  # wimax_4g_usb - (optional) is a type of string
  wimax_4g_usb = var.wimax_4g_usb
  # wireless_controller - (optional) is a type of string
  wireless_controller = var.wireless_controller
  # wireless_controller_port - (optional) is a type of number
  wireless_controller_port = var.wireless_controller_port
}
```

[top](#index)

### Outputs

```terraform
output "admin_concurrent" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_concurrent
}

output "admin_console_timeout" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_console_timeout
}

output "admin_hsts_max_age" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_hsts_max_age
}

output "admin_https_pki_required" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_https_pki_required
}

output "admin_https_redirect" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_https_redirect
}

output "admin_https_ssl_versions" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_https_ssl_versions
}

output "admin_lockout_duration" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_lockout_duration
}

output "admin_lockout_threshold" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_lockout_threshold
}

output "admin_login_max" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_login_max
}

output "admin_maintainer" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_maintainer
}

output "admin_port" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_port
}

output "admin_restrict_local" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_restrict_local
}

output "admin_scp" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_scp
}

output "admin_server_cert" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_server_cert
}

output "admin_sport" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_sport
}

output "admin_ssh_grace_time" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_ssh_grace_time
}

output "admin_ssh_password" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_ssh_password
}

output "admin_ssh_port" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_ssh_port
}

output "admin_ssh_v1" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_ssh_v1
}

output "admin_telnet" {
  description = "returns a string"
  value       = fortios_system_global.this.admin_telnet
}

output "admin_telnet_port" {
  description = "returns a number"
  value       = fortios_system_global.this.admin_telnet_port
}

output "admintimeout" {
  description = "returns a number"
  value       = fortios_system_global.this.admintimeout
}

output "alias" {
  description = "returns a string"
  value       = fortios_system_global.this.alias
}

output "allow_traffic_redirect" {
  description = "returns a string"
  value       = fortios_system_global.this.allow_traffic_redirect
}

output "anti_replay" {
  description = "returns a string"
  value       = fortios_system_global.this.anti_replay
}

output "arp_max_entry" {
  description = "returns a number"
  value       = fortios_system_global.this.arp_max_entry
}

output "asymroute" {
  description = "returns a string"
  value       = fortios_system_global.this.asymroute
}

output "auth_cert" {
  description = "returns a string"
  value       = fortios_system_global.this.auth_cert
}

output "auth_http_port" {
  description = "returns a number"
  value       = fortios_system_global.this.auth_http_port
}

output "auth_https_port" {
  description = "returns a number"
  value       = fortios_system_global.this.auth_https_port
}

output "auth_keepalive" {
  description = "returns a string"
  value       = fortios_system_global.this.auth_keepalive
}

output "auth_session_limit" {
  description = "returns a string"
  value       = fortios_system_global.this.auth_session_limit
}

output "auto_auth_extension_device" {
  description = "returns a string"
  value       = fortios_system_global.this.auto_auth_extension_device
}

output "autorun_log_fsck" {
  description = "returns a string"
  value       = fortios_system_global.this.autorun_log_fsck
}

output "av_affinity" {
  description = "returns a string"
  value       = fortios_system_global.this.av_affinity
}

output "av_failopen" {
  description = "returns a string"
  value       = fortios_system_global.this.av_failopen
}

output "av_failopen_session" {
  description = "returns a string"
  value       = fortios_system_global.this.av_failopen_session
}

output "batch_cmdb" {
  description = "returns a string"
  value       = fortios_system_global.this.batch_cmdb
}

output "block_session_timer" {
  description = "returns a number"
  value       = fortios_system_global.this.block_session_timer
}

output "br_fdb_max_entry" {
  description = "returns a number"
  value       = fortios_system_global.this.br_fdb_max_entry
}

output "cert_chain_max" {
  description = "returns a number"
  value       = fortios_system_global.this.cert_chain_max
}

output "cfg_revert_timeout" {
  description = "returns a number"
  value       = fortios_system_global.this.cfg_revert_timeout
}

output "cfg_save" {
  description = "returns a string"
  value       = fortios_system_global.this.cfg_save
}

output "check_protocol_header" {
  description = "returns a string"
  value       = fortios_system_global.this.check_protocol_header
}

output "check_reset_range" {
  description = "returns a string"
  value       = fortios_system_global.this.check_reset_range
}

output "cli_audit_log" {
  description = "returns a string"
  value       = fortios_system_global.this.cli_audit_log
}

output "cloud_communication" {
  description = "returns a string"
  value       = fortios_system_global.this.cloud_communication
}

output "clt_cert_req" {
  description = "returns a string"
  value       = fortios_system_global.this.clt_cert_req
}

output "compliance_check" {
  description = "returns a string"
  value       = fortios_system_global.this.compliance_check
}

output "compliance_check_time" {
  description = "returns a string"
  value       = fortios_system_global.this.compliance_check_time
}

output "cpu_use_threshold" {
  description = "returns a number"
  value       = fortios_system_global.this.cpu_use_threshold
}

output "csr_ca_attribute" {
  description = "returns a string"
  value       = fortios_system_global.this.csr_ca_attribute
}

output "daily_restart" {
  description = "returns a string"
  value       = fortios_system_global.this.daily_restart
}

output "default_service_source_port" {
  description = "returns a string"
  value       = fortios_system_global.this.default_service_source_port
}

output "device_identification_active_scan_delay" {
  description = "returns a number"
  value       = fortios_system_global.this.device_identification_active_scan_delay
}

output "device_idle_timeout" {
  description = "returns a number"
  value       = fortios_system_global.this.device_idle_timeout
}

output "dh_params" {
  description = "returns a string"
  value       = fortios_system_global.this.dh_params
}

output "dnsproxy_worker_count" {
  description = "returns a number"
  value       = fortios_system_global.this.dnsproxy_worker_count
}

output "dst" {
  description = "returns a string"
  value       = fortios_system_global.this.dst
}

output "endpoint_control_fds_access" {
  description = "returns a string"
  value       = fortios_system_global.this.endpoint_control_fds_access
}

output "endpoint_control_portal_port" {
  description = "returns a number"
  value       = fortios_system_global.this.endpoint_control_portal_port
}

output "failtime" {
  description = "returns a number"
  value       = fortios_system_global.this.failtime
}

output "faz_disk_buffer_size" {
  description = "returns a number"
  value       = fortios_system_global.this.faz_disk_buffer_size
}

output "fds_statistics" {
  description = "returns a string"
  value       = fortios_system_global.this.fds_statistics
}

output "fds_statistics_period" {
  description = "returns a number"
  value       = fortios_system_global.this.fds_statistics_period
}

output "fec_port" {
  description = "returns a number"
  value       = fortios_system_global.this.fec_port
}

output "fgd_alert_subscription" {
  description = "returns a string"
  value       = fortios_system_global.this.fgd_alert_subscription
}

output "fortiextender" {
  description = "returns a string"
  value       = fortios_system_global.this.fortiextender
}

output "fortiextender_data_port" {
  description = "returns a number"
  value       = fortios_system_global.this.fortiextender_data_port
}

output "fortiextender_vlan_mode" {
  description = "returns a string"
  value       = fortios_system_global.this.fortiextender_vlan_mode
}

output "fortiipam_integration" {
  description = "returns a string"
  value       = fortios_system_global.this.fortiipam_integration
}

output "fortiservice_port" {
  description = "returns a number"
  value       = fortios_system_global.this.fortiservice_port
}

output "fortitoken_cloud" {
  description = "returns a string"
  value       = fortios_system_global.this.fortitoken_cloud
}

output "gui_allow_default_hostname" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_allow_default_hostname
}

output "gui_certificates" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_certificates
}

output "gui_custom_language" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_custom_language
}

output "gui_date_format" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_date_format
}

output "gui_date_time_source" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_date_time_source
}

output "gui_device_latitude" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_device_latitude
}

output "gui_device_longitude" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_device_longitude
}

output "gui_display_hostname" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_display_hostname
}

output "gui_firmware_upgrade_setup_warning" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_firmware_upgrade_setup_warning
}

output "gui_firmware_upgrade_warning" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_firmware_upgrade_warning
}

output "gui_forticare_registration_setup_warning" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_forticare_registration_setup_warning
}

output "gui_fortigate_cloud_sandbox" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_fortigate_cloud_sandbox
}

output "gui_fortisandbox_cloud" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_fortisandbox_cloud
}

output "gui_ipv6" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_ipv6
}

output "gui_lines_per_page" {
  description = "returns a number"
  value       = fortios_system_global.this.gui_lines_per_page
}

output "gui_theme" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_theme
}

output "gui_wireless_opensecurity" {
  description = "returns a string"
  value       = fortios_system_global.this.gui_wireless_opensecurity
}

output "honor_df" {
  description = "returns a string"
  value       = fortios_system_global.this.honor_df
}

output "hostname" {
  description = "returns a string"
  value       = fortios_system_global.this.hostname
}

output "id" {
  description = "returns a string"
  value       = fortios_system_global.this.id
}

output "igmp_state_limit" {
  description = "returns a number"
  value       = fortios_system_global.this.igmp_state_limit
}

output "ike_embryonic_limit" {
  description = "returns a number"
  value       = fortios_system_global.this.ike_embryonic_limit
}

output "interval" {
  description = "returns a number"
  value       = fortios_system_global.this.interval
}

output "ip_src_port_range" {
  description = "returns a string"
  value       = fortios_system_global.this.ip_src_port_range
}

output "ips_affinity" {
  description = "returns a string"
  value       = fortios_system_global.this.ips_affinity
}

output "ipsec_asic_offload" {
  description = "returns a string"
  value       = fortios_system_global.this.ipsec_asic_offload
}

output "ipsec_hmac_offload" {
  description = "returns a string"
  value       = fortios_system_global.this.ipsec_hmac_offload
}

output "ipsec_soft_dec_async" {
  description = "returns a string"
  value       = fortios_system_global.this.ipsec_soft_dec_async
}

output "ipv6_accept_dad" {
  description = "returns a number"
  value       = fortios_system_global.this.ipv6_accept_dad
}

output "ipv6_allow_anycast_probe" {
  description = "returns a string"
  value       = fortios_system_global.this.ipv6_allow_anycast_probe
}

output "ipv6_allow_traffic_redirect" {
  description = "returns a string"
  value       = fortios_system_global.this.ipv6_allow_traffic_redirect
}

output "irq_time_accounting" {
  description = "returns a string"
  value       = fortios_system_global.this.irq_time_accounting
}

output "language" {
  description = "returns a string"
  value       = fortios_system_global.this.language
}

output "ldapconntimeout" {
  description = "returns a number"
  value       = fortios_system_global.this.ldapconntimeout
}

output "lldp_reception" {
  description = "returns a string"
  value       = fortios_system_global.this.lldp_reception
}

output "lldp_transmission" {
  description = "returns a string"
  value       = fortios_system_global.this.lldp_transmission
}

output "log_ssl_connection" {
  description = "returns a string"
  value       = fortios_system_global.this.log_ssl_connection
}

output "log_uuid_address" {
  description = "returns a string"
  value       = fortios_system_global.this.log_uuid_address
}

output "log_uuid_policy" {
  description = "returns a string"
  value       = fortios_system_global.this.log_uuid_policy
}

output "login_timestamp" {
  description = "returns a string"
  value       = fortios_system_global.this.login_timestamp
}

output "long_vdom_name" {
  description = "returns a string"
  value       = fortios_system_global.this.long_vdom_name
}

output "management_vdom" {
  description = "returns a string"
  value       = fortios_system_global.this.management_vdom
}

output "max_dlpstat_memory" {
  description = "returns a number"
  value       = fortios_system_global.this.max_dlpstat_memory
}

output "max_route_cache_size" {
  description = "returns a number"
  value       = fortios_system_global.this.max_route_cache_size
}

output "mc_ttl_notchange" {
  description = "returns a string"
  value       = fortios_system_global.this.mc_ttl_notchange
}

output "memory_use_threshold_extreme" {
  description = "returns a number"
  value       = fortios_system_global.this.memory_use_threshold_extreme
}

output "memory_use_threshold_green" {
  description = "returns a number"
  value       = fortios_system_global.this.memory_use_threshold_green
}

output "memory_use_threshold_red" {
  description = "returns a number"
  value       = fortios_system_global.this.memory_use_threshold_red
}

output "miglog_affinity" {
  description = "returns a string"
  value       = fortios_system_global.this.miglog_affinity
}

output "miglogd_children" {
  description = "returns a number"
  value       = fortios_system_global.this.miglogd_children
}

output "multi_factor_authentication" {
  description = "returns a string"
  value       = fortios_system_global.this.multi_factor_authentication
}

output "multicast_forward" {
  description = "returns a string"
  value       = fortios_system_global.this.multicast_forward
}

output "ndp_max_entry" {
  description = "returns a number"
  value       = fortios_system_global.this.ndp_max_entry
}

output "per_user_bal" {
  description = "returns a string"
  value       = fortios_system_global.this.per_user_bal
}

output "per_user_bwl" {
  description = "returns a string"
  value       = fortios_system_global.this.per_user_bwl
}

output "policy_auth_concurrent" {
  description = "returns a number"
  value       = fortios_system_global.this.policy_auth_concurrent
}

output "post_login_banner" {
  description = "returns a string"
  value       = fortios_system_global.this.post_login_banner
}

output "pre_login_banner" {
  description = "returns a string"
  value       = fortios_system_global.this.pre_login_banner
}

output "private_data_encryption" {
  description = "returns a string"
  value       = fortios_system_global.this.private_data_encryption
}

output "proxy_auth_lifetime" {
  description = "returns a string"
  value       = fortios_system_global.this.proxy_auth_lifetime
}

output "proxy_auth_lifetime_timeout" {
  description = "returns a number"
  value       = fortios_system_global.this.proxy_auth_lifetime_timeout
}

output "proxy_auth_timeout" {
  description = "returns a number"
  value       = fortios_system_global.this.proxy_auth_timeout
}

output "proxy_cipher_hardware_acceleration" {
  description = "returns a string"
  value       = fortios_system_global.this.proxy_cipher_hardware_acceleration
}

output "proxy_kxp_hardware_acceleration" {
  description = "returns a string"
  value       = fortios_system_global.this.proxy_kxp_hardware_acceleration
}

output "proxy_re_authentication_mode" {
  description = "returns a string"
  value       = fortios_system_global.this.proxy_re_authentication_mode
}

output "proxy_worker_count" {
  description = "returns a number"
  value       = fortios_system_global.this.proxy_worker_count
}

output "radius_port" {
  description = "returns a number"
  value       = fortios_system_global.this.radius_port
}

output "reboot_upon_config_restore" {
  description = "returns a string"
  value       = fortios_system_global.this.reboot_upon_config_restore
}

output "refresh" {
  description = "returns a number"
  value       = fortios_system_global.this.refresh
}

output "remoteauthtimeout" {
  description = "returns a number"
  value       = fortios_system_global.this.remoteauthtimeout
}

output "reset_sessionless_tcp" {
  description = "returns a string"
  value       = fortios_system_global.this.reset_sessionless_tcp
}

output "restart_time" {
  description = "returns a string"
  value       = fortios_system_global.this.restart_time
}

output "revision_backup_on_logout" {
  description = "returns a string"
  value       = fortios_system_global.this.revision_backup_on_logout
}

output "revision_image_auto_backup" {
  description = "returns a string"
  value       = fortios_system_global.this.revision_image_auto_backup
}

output "scanunit_count" {
  description = "returns a number"
  value       = fortios_system_global.this.scanunit_count
}

output "security_rating_result_submission" {
  description = "returns a string"
  value       = fortios_system_global.this.security_rating_result_submission
}

output "security_rating_run_on_schedule" {
  description = "returns a string"
  value       = fortios_system_global.this.security_rating_run_on_schedule
}

output "send_pmtu_icmp" {
  description = "returns a string"
  value       = fortios_system_global.this.send_pmtu_icmp
}

output "snat_route_change" {
  description = "returns a string"
  value       = fortios_system_global.this.snat_route_change
}

output "special_file_23_support" {
  description = "returns a string"
  value       = fortios_system_global.this.special_file_23_support
}

output "ssd_trim_date" {
  description = "returns a number"
  value       = fortios_system_global.this.ssd_trim_date
}

output "ssd_trim_freq" {
  description = "returns a string"
  value       = fortios_system_global.this.ssd_trim_freq
}

output "ssd_trim_hour" {
  description = "returns a number"
  value       = fortios_system_global.this.ssd_trim_hour
}

output "ssd_trim_min" {
  description = "returns a number"
  value       = fortios_system_global.this.ssd_trim_min
}

output "ssd_trim_weekday" {
  description = "returns a string"
  value       = fortios_system_global.this.ssd_trim_weekday
}

output "ssh_cbc_cipher" {
  description = "returns a string"
  value       = fortios_system_global.this.ssh_cbc_cipher
}

output "ssh_hmac_md5" {
  description = "returns a string"
  value       = fortios_system_global.this.ssh_hmac_md5
}

output "ssh_kex_sha1" {
  description = "returns a string"
  value       = fortios_system_global.this.ssh_kex_sha1
}

output "ssh_mac_weak" {
  description = "returns a string"
  value       = fortios_system_global.this.ssh_mac_weak
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_system_global.this.ssl_min_proto_version
}

output "ssl_static_key_ciphers" {
  description = "returns a string"
  value       = fortios_system_global.this.ssl_static_key_ciphers
}

output "sslvpn_cipher_hardware_acceleration" {
  description = "returns a string"
  value       = fortios_system_global.this.sslvpn_cipher_hardware_acceleration
}

output "sslvpn_ems_sn_check" {
  description = "returns a string"
  value       = fortios_system_global.this.sslvpn_ems_sn_check
}

output "sslvpn_kxp_hardware_acceleration" {
  description = "returns a string"
  value       = fortios_system_global.this.sslvpn_kxp_hardware_acceleration
}

output "sslvpn_max_worker_count" {
  description = "returns a number"
  value       = fortios_system_global.this.sslvpn_max_worker_count
}

output "sslvpn_plugin_version_check" {
  description = "returns a string"
  value       = fortios_system_global.this.sslvpn_plugin_version_check
}

output "strict_dirty_session_check" {
  description = "returns a string"
  value       = fortios_system_global.this.strict_dirty_session_check
}

output "strong_crypto" {
  description = "returns a string"
  value       = fortios_system_global.this.strong_crypto
}

output "switch_controller" {
  description = "returns a string"
  value       = fortios_system_global.this.switch_controller
}

output "switch_controller_reserved_network" {
  description = "returns a string"
  value       = fortios_system_global.this.switch_controller_reserved_network
}

output "sys_perf_log_interval" {
  description = "returns a number"
  value       = fortios_system_global.this.sys_perf_log_interval
}

output "tcp_halfclose_timer" {
  description = "returns a number"
  value       = fortios_system_global.this.tcp_halfclose_timer
}

output "tcp_halfopen_timer" {
  description = "returns a number"
  value       = fortios_system_global.this.tcp_halfopen_timer
}

output "tcp_option" {
  description = "returns a string"
  value       = fortios_system_global.this.tcp_option
}

output "tcp_timewait_timer" {
  description = "returns a number"
  value       = fortios_system_global.this.tcp_timewait_timer
}

output "tftp" {
  description = "returns a string"
  value       = fortios_system_global.this.tftp
}

output "timezone" {
  description = "returns a string"
  value       = fortios_system_global.this.timezone
}

output "tp_mc_skip_policy" {
  description = "returns a string"
  value       = fortios_system_global.this.tp_mc_skip_policy
}

output "traffic_priority" {
  description = "returns a string"
  value       = fortios_system_global.this.traffic_priority
}

output "traffic_priority_level" {
  description = "returns a string"
  value       = fortios_system_global.this.traffic_priority_level
}

output "two_factor_email_expiry" {
  description = "returns a number"
  value       = fortios_system_global.this.two_factor_email_expiry
}

output "two_factor_fac_expiry" {
  description = "returns a number"
  value       = fortios_system_global.this.two_factor_fac_expiry
}

output "two_factor_ftk_expiry" {
  description = "returns a number"
  value       = fortios_system_global.this.two_factor_ftk_expiry
}

output "two_factor_ftm_expiry" {
  description = "returns a number"
  value       = fortios_system_global.this.two_factor_ftm_expiry
}

output "two_factor_sms_expiry" {
  description = "returns a number"
  value       = fortios_system_global.this.two_factor_sms_expiry
}

output "udp_idle_timer" {
  description = "returns a number"
  value       = fortios_system_global.this.udp_idle_timer
}

output "url_filter_affinity" {
  description = "returns a string"
  value       = fortios_system_global.this.url_filter_affinity
}

output "url_filter_count" {
  description = "returns a number"
  value       = fortios_system_global.this.url_filter_count
}

output "user_device_store_max_devices" {
  description = "returns a number"
  value       = fortios_system_global.this.user_device_store_max_devices
}

output "user_device_store_max_users" {
  description = "returns a number"
  value       = fortios_system_global.this.user_device_store_max_users
}

output "user_server_cert" {
  description = "returns a string"
  value       = fortios_system_global.this.user_server_cert
}

output "vdom_admin" {
  description = "returns a string"
  value       = fortios_system_global.this.vdom_admin
}

output "vdom_mode" {
  description = "returns a string"
  value       = fortios_system_global.this.vdom_mode
}

output "vip_arp_range" {
  description = "returns a string"
  value       = fortios_system_global.this.vip_arp_range
}

output "virtual_server_count" {
  description = "returns a number"
  value       = fortios_system_global.this.virtual_server_count
}

output "virtual_server_hardware_acceleration" {
  description = "returns a string"
  value       = fortios_system_global.this.virtual_server_hardware_acceleration
}

output "wad_affinity" {
  description = "returns a string"
  value       = fortios_system_global.this.wad_affinity
}

output "wad_csvc_cs_count" {
  description = "returns a number"
  value       = fortios_system_global.this.wad_csvc_cs_count
}

output "wad_csvc_db_count" {
  description = "returns a number"
  value       = fortios_system_global.this.wad_csvc_db_count
}

output "wad_memory_change_granularity" {
  description = "returns a number"
  value       = fortios_system_global.this.wad_memory_change_granularity
}

output "wad_source_affinity" {
  description = "returns a string"
  value       = fortios_system_global.this.wad_source_affinity
}

output "wad_worker_count" {
  description = "returns a number"
  value       = fortios_system_global.this.wad_worker_count
}

output "wifi_ca_certificate" {
  description = "returns a string"
  value       = fortios_system_global.this.wifi_ca_certificate
}

output "wifi_certificate" {
  description = "returns a string"
  value       = fortios_system_global.this.wifi_certificate
}

output "wimax_4g_usb" {
  description = "returns a string"
  value       = fortios_system_global.this.wimax_4g_usb
}

output "wireless_controller" {
  description = "returns a string"
  value       = fortios_system_global.this.wireless_controller
}

output "wireless_controller_port" {
  description = "returns a number"
  value       = fortios_system_global.this.wireless_controller_port
}

output "this" {
  value = fortios_system_global.this
}
```

[top](#index)