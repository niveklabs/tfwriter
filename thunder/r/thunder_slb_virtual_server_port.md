# thunder_slb_virtual_server_port

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
module "thunder_slb_virtual_server_port" {
  source = "./modules/thunder/r/thunder_slb_virtual_server_port"

  # action - (optional) is a type of string
  action = null
  # alt_protocol1 - (optional) is a type of string
  alt_protocol1 = null
  # alt_protocol2 - (optional) is a type of string
  alt_protocol2 = null
  # alternate_port - (optional) is a type of number
  alternate_port = null
  # alternate_port_number - (optional) is a type of number
  alternate_port_number = null
  # auto - (optional) is a type of number
  auto = null
  # clientip_sticky_nat - (optional) is a type of number
  clientip_sticky_nat = null
  # conn_limit - (optional) is a type of number
  conn_limit = null
  # cpu_compute - (optional) is a type of number
  cpu_compute = null
  # def_selection_if_pref_failed - (optional) is a type of string
  def_selection_if_pref_failed = null
  # enable_playerid_check - (optional) is a type of number
  enable_playerid_check = null
  # eth_fwd - (optional) is a type of number
  eth_fwd = null
  # eth_rev - (optional) is a type of number
  eth_rev = null
  # expand - (optional) is a type of number
  expand = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # force_routing_mode - (optional) is a type of number
  force_routing_mode = null
  # gslb_enable - (optional) is a type of number
  gslb_enable = null
  # gtp_session_lb - (optional) is a type of number
  gtp_session_lb = null
  # ha_conn_mirror - (optional) is a type of number
  ha_conn_mirror = null
  # ignore_global - (optional) is a type of number
  ignore_global = null
  # ip_map_list - (optional) is a type of string
  ip_map_list = null
  # ipinip - (optional) is a type of number
  ipinip = null
  # l7_hardware_assist - (optional) is a type of number
  l7_hardware_assist = null
  # memory_compute - (optional) is a type of number
  memory_compute = null
  # message_switching - (optional) is a type of number
  message_switching = null
  # name - (optional) is a type of string
  name = null
  # no_auto_up_on_aflex - (optional) is a type of number
  no_auto_up_on_aflex = null
  # no_dest_nat - (optional) is a type of number
  no_dest_nat = null
  # no_logging - (optional) is a type of number
  no_logging = null
  # on_syn - (optional) is a type of number
  on_syn = null
  # optimization_level - (optional) is a type of string
  optimization_level = null
  # p_template_sip_shared - (optional) is a type of number
  p_template_sip_shared = null
  # persist_type - (optional) is a type of string
  persist_type = null
  # pool - (optional) is a type of string
  pool = null
  # pool_shared - (optional) is a type of string
  pool_shared = null
  # port_number - (optional) is a type of number
  port_number = null
  # port_translation - (optional) is a type of number
  port_translation = null
  # precedence - (optional) is a type of number
  precedence = null
  # protocol - (optional) is a type of string
  protocol = null
  # range - (optional) is a type of number
  range = null
  # rate - (optional) is a type of number
  rate = null
  # redirect_to_https - (optional) is a type of number
  redirect_to_https = null
  # req_fail - (optional) is a type of number
  req_fail = null
  # reset - (optional) is a type of number
  reset = null
  # reset_on_server_selection_fail - (optional) is a type of number
  reset_on_server_selection_fail = null
  # rtp_sip_call_id_match - (optional) is a type of number
  rtp_sip_call_id_match = null
  # scaleout_bucket_count - (optional) is a type of number
  scaleout_bucket_count = null
  # scaleout_device_group - (optional) is a type of number
  scaleout_device_group = null
  # secs - (optional) is a type of number
  secs = null
  # serv_sel_fail - (optional) is a type of number
  serv_sel_fail = null
  # service_group - (optional) is a type of string
  service_group = null
  # shared_partition_cache_template - (optional) is a type of number
  shared_partition_cache_template = null
  # shared_partition_client_ssl_template - (optional) is a type of number
  shared_partition_client_ssl_template = null
  # shared_partition_connection_reuse_template - (optional) is a type of number
  shared_partition_connection_reuse_template = null
  # shared_partition_dblb_template - (optional) is a type of number
  shared_partition_dblb_template = null
  # shared_partition_diameter_template - (optional) is a type of number
  shared_partition_diameter_template = null
  # shared_partition_dns_template - (optional) is a type of number
  shared_partition_dns_template = null
  # shared_partition_doh_template - (optional) is a type of number
  shared_partition_doh_template = null
  # shared_partition_dynamic_service_template - (optional) is a type of number
  shared_partition_dynamic_service_template = null
  # shared_partition_external_service_template - (optional) is a type of number
  shared_partition_external_service_template = null
  # shared_partition_fix_template - (optional) is a type of number
  shared_partition_fix_template = null
  # shared_partition_http_policy_template - (optional) is a type of number
  shared_partition_http_policy_template = null
  # shared_partition_http_template - (optional) is a type of number
  shared_partition_http_template = null
  # shared_partition_imap_pop3_template - (optional) is a type of number
  shared_partition_imap_pop3_template = null
  # shared_partition_persist_cookie_template - (optional) is a type of number
  shared_partition_persist_cookie_template = null
  # shared_partition_persist_destination_ip_template - (optional) is a type of number
  shared_partition_persist_destination_ip_template = null
  # shared_partition_persist_source_ip_template - (optional) is a type of number
  shared_partition_persist_source_ip_template = null
  # shared_partition_persist_ssl_sid_template - (optional) is a type of number
  shared_partition_persist_ssl_sid_template = null
  # shared_partition_policy_template - (optional) is a type of number
  shared_partition_policy_template = null
  # shared_partition_pool - (optional) is a type of number
  shared_partition_pool = null
  # shared_partition_server_ssl_template - (optional) is a type of number
  shared_partition_server_ssl_template = null
  # shared_partition_smpp_template - (optional) is a type of number
  shared_partition_smpp_template = null
  # shared_partition_smtp_template - (optional) is a type of number
  shared_partition_smtp_template = null
  # shared_partition_tcp - (optional) is a type of number
  shared_partition_tcp = null
  # shared_partition_tcp_proxy_template - (optional) is a type of number
  shared_partition_tcp_proxy_template = null
  # shared_partition_udp - (optional) is a type of number
  shared_partition_udp = null
  # shared_partition_virtual_port_template - (optional) is a type of number
  shared_partition_virtual_port_template = null
  # skip_rev_hash - (optional) is a type of number
  skip_rev_hash = null
  # snat_on_vip - (optional) is a type of number
  snat_on_vip = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
  # substitute_source_mac - (optional) is a type of number
  substitute_source_mac = null
  # support_http2 - (optional) is a type of number
  support_http2 = null
  # syn_cookie - (optional) is a type of number
  syn_cookie = null
  # template_cache - (optional) is a type of string
  template_cache = null
  # template_cache_shared - (optional) is a type of string
  template_cache_shared = null
  # template_client_ssh - (optional) is a type of string
  template_client_ssh = null
  # template_client_ssl - (optional) is a type of string
  template_client_ssl = null
  # template_client_ssl_shared - (optional) is a type of string
  template_client_ssl_shared = null
  # template_connection_reuse - (optional) is a type of string
  template_connection_reuse = null
  # template_connection_reuse_shared - (optional) is a type of string
  template_connection_reuse_shared = null
  # template_dblb - (optional) is a type of string
  template_dblb = null
  # template_dblb_shared - (optional) is a type of string
  template_dblb_shared = null
  # template_diameter - (optional) is a type of string
  template_diameter = null
  # template_diameter_shared - (optional) is a type of string
  template_diameter_shared = null
  # template_dns - (optional) is a type of string
  template_dns = null
  # template_dns_shared - (optional) is a type of string
  template_dns_shared = null
  # template_doh - (optional) is a type of string
  template_doh = null
  # template_doh_shared - (optional) is a type of string
  template_doh_shared = null
  # template_dynamic_service - (optional) is a type of string
  template_dynamic_service = null
  # template_dynamic_service_shared - (optional) is a type of string
  template_dynamic_service_shared = null
  # template_external_service - (optional) is a type of string
  template_external_service = null
  # template_external_service_shared - (optional) is a type of string
  template_external_service_shared = null
  # template_file_inspection - (optional) is a type of string
  template_file_inspection = null
  # template_fix - (optional) is a type of string
  template_fix = null
  # template_fix_shared - (optional) is a type of string
  template_fix_shared = null
  # template_ftp - (optional) is a type of string
  template_ftp = null
  # template_http - (optional) is a type of string
  template_http = null
  # template_http_policy - (optional) is a type of string
  template_http_policy = null
  # template_http_policy_shared - (optional) is a type of string
  template_http_policy_shared = null
  # template_http_shared - (optional) is a type of string
  template_http_shared = null
  # template_imap_pop3 - (optional) is a type of string
  template_imap_pop3 = null
  # template_imap_pop3_shared - (optional) is a type of string
  template_imap_pop3_shared = null
  # template_mqtt - (optional) is a type of string
  template_mqtt = null
  # template_persist_cookie - (optional) is a type of string
  template_persist_cookie = null
  # template_persist_cookie_shared - (optional) is a type of string
  template_persist_cookie_shared = null
  # template_persist_destination_ip - (optional) is a type of string
  template_persist_destination_ip = null
  # template_persist_destination_ip_shared - (optional) is a type of string
  template_persist_destination_ip_shared = null
  # template_persist_source_ip - (optional) is a type of string
  template_persist_source_ip = null
  # template_persist_source_ip_shared - (optional) is a type of string
  template_persist_source_ip_shared = null
  # template_persist_ssl_sid - (optional) is a type of string
  template_persist_ssl_sid = null
  # template_persist_ssl_sid_shared - (optional) is a type of string
  template_persist_ssl_sid_shared = null
  # template_policy - (optional) is a type of string
  template_policy = null
  # template_policy_shared - (optional) is a type of string
  template_policy_shared = null
  # template_reqmod_icap - (optional) is a type of string
  template_reqmod_icap = null
  # template_respmod_icap - (optional) is a type of string
  template_respmod_icap = null
  # template_scaleout - (optional) is a type of string
  template_scaleout = null
  # template_server_ssh - (optional) is a type of string
  template_server_ssh = null
  # template_server_ssl - (optional) is a type of string
  template_server_ssl = null
  # template_server_ssl_shared - (optional) is a type of string
  template_server_ssl_shared = null
  # template_sip - (optional) is a type of string
  template_sip = null
  # template_sip_shared - (optional) is a type of string
  template_sip_shared = null
  # template_smpp - (optional) is a type of string
  template_smpp = null
  # template_smpp_shared - (optional) is a type of string
  template_smpp_shared = null
  # template_smtp - (optional) is a type of string
  template_smtp = null
  # template_smtp_shared - (optional) is a type of string
  template_smtp_shared = null
  # template_ssli - (optional) is a type of string
  template_ssli = null
  # template_tcp - (optional) is a type of string
  template_tcp = null
  # template_tcp_proxy - (optional) is a type of string
  template_tcp_proxy = null
  # template_tcp_proxy_client - (optional) is a type of string
  template_tcp_proxy_client = null
  # template_tcp_proxy_server - (optional) is a type of string
  template_tcp_proxy_server = null
  # template_tcp_proxy_shared - (optional) is a type of string
  template_tcp_proxy_shared = null
  # template_tcp_shared - (optional) is a type of string
  template_tcp_shared = null
  # template_udp - (optional) is a type of string
  template_udp = null
  # template_udp_shared - (optional) is a type of string
  template_udp_shared = null
  # template_virtual_port - (optional) is a type of string
  template_virtual_port = null
  # template_virtual_port_shared - (optional) is a type of string
  template_virtual_port_shared = null
  # trunk_fwd - (optional) is a type of number
  trunk_fwd = null
  # trunk_rev - (optional) is a type of number
  trunk_rev = null
  # use_alternate_port - (optional) is a type of number
  use_alternate_port = null
  # use_cgnv6 - (optional) is a type of number
  use_cgnv6 = null
  # use_default_if_no_server - (optional) is a type of number
  use_default_if_no_server = null
  # use_rcv_hop_for_resp - (optional) is a type of number
  use_rcv_hop_for_resp = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # view - (optional) is a type of number
  view = null
  # waf_template - (optional) is a type of string
  waf_template = null
  # when_down - (optional) is a type of number
  when_down = null
  # when_down_protocol2 - (optional) is a type of number
  when_down_protocol2 = null

  acl_id_list = [{
    acl_id                       = null
    acl_id_seq_num               = null
    acl_id_seq_num_shared        = null
    acl_id_shared                = null
    acl_id_src_nat_pool          = null
    acl_id_src_nat_pool_shared   = null
    shared_partition_pool_id     = null
    v_acl_id_seq_num             = null
    v_acl_id_seq_num_shared      = null
    v_acl_id_src_nat_pool        = null
    v_acl_id_src_nat_pool_shared = null
    v_shared_partition_pool_id   = null
  }]

  acl_name_list = [{
    acl_name                       = null
    acl_name_seq_num               = null
    acl_name_seq_num_shared        = null
    acl_name_shared                = null
    acl_name_src_nat_pool          = null
    acl_name_src_nat_pool_shared   = null
    shared_partition_pool_name     = null
    v_acl_name_seq_num             = null
    v_acl_name_seq_num_shared      = null
    v_acl_name_src_nat_pool        = null
    v_acl_name_src_nat_pool_shared = null
    v_shared_partition_pool_name   = null
  }]

  aflex_scripts = [{
    aflex        = null
    aflex_shared = null
  }]

  auth_cfg = [{
    aaa_policy = null
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

variable "alt_protocol1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alt_protocol2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alternate_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "alternate_port_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "clientip_sticky_nat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cpu_compute" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "def_selection_if_pref_failed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_playerid_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eth_fwd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eth_rev" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "expand" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_stats" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "force_routing_mode" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gslb_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gtp_session_lb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ha_conn_mirror" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ignore_global" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_map_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipinip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "l7_hardware_assist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "memory_compute" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "message_switching" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "no_auto_up_on_aflex" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "no_dest_nat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "on_syn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "optimization_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "p_template_sip_shared" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "persist_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_translation" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "precedence" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "range" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "redirect_to_https" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "req_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_on_server_selection_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rtp_sip_call_id_match" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scaleout_bucket_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scaleout_device_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "serv_sel_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared_partition_cache_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_client_ssl_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_connection_reuse_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_dblb_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_diameter_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_dns_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_doh_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_dynamic_service_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_external_service_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_fix_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_http_policy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_http_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_imap_pop3_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_persist_cookie_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_persist_destination_ip_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_persist_source_ip_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_persist_ssl_sid_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_policy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_pool" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_server_ssl_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_smpp_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_smtp_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_tcp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_tcp_proxy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_udp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_virtual_port_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "skip_rev_hash" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat_on_vip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stats_data_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "substitute_source_mac" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "support_http2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "syn_cookie" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template_cache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_cache_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_client_ssh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_client_ssl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_client_ssl_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_connection_reuse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_connection_reuse_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_dblb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_dblb_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_diameter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_diameter_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_dns_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_doh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_doh_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_dynamic_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_dynamic_service_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_external_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_external_service_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_file_inspection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_fix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_fix_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_ftp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_http" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_http_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_http_policy_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_http_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_imap_pop3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_imap_pop3_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_mqtt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_cookie" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_cookie_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_destination_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_destination_ip_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_source_ip_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_ssl_sid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_ssl_sid_shared" {
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

variable "template_reqmod_icap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_respmod_icap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_scaleout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_server_ssh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_server_ssl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_server_ssl_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_sip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_sip_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_smpp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_smpp_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_smtp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_smtp_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_ssli" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp_proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp_proxy_client" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp_proxy_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp_proxy_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_udp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_udp_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_virtual_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_virtual_port_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trunk_fwd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trunk_rev" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_alternate_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_cgnv6" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_default_if_no_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_rcv_hop_for_resp" {
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

variable "view" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "waf_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "when_down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "when_down_protocol2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "acl_id_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      acl_id                       = number
      acl_id_seq_num               = number
      acl_id_seq_num_shared        = number
      acl_id_shared                = number
      acl_id_src_nat_pool          = string
      acl_id_src_nat_pool_shared   = string
      shared_partition_pool_id     = number
      v_acl_id_seq_num             = number
      v_acl_id_seq_num_shared      = number
      v_acl_id_src_nat_pool        = string
      v_acl_id_src_nat_pool_shared = string
      v_shared_partition_pool_id   = number
    }
  ))
  default = []
}

variable "acl_name_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      acl_name                       = string
      acl_name_seq_num               = number
      acl_name_seq_num_shared        = number
      acl_name_shared                = string
      acl_name_src_nat_pool          = string
      acl_name_src_nat_pool_shared   = string
      shared_partition_pool_name     = number
      v_acl_name_seq_num             = number
      v_acl_name_seq_num_shared      = number
      v_acl_name_src_nat_pool        = string
      v_acl_name_src_nat_pool_shared = string
      v_shared_partition_pool_name   = number
    }
  ))
  default = []
}

variable "aflex_scripts" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      aflex        = string
      aflex_shared = string
    }
  ))
  default = []
}

variable "auth_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aaa_policy = string
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
resource "thunder_slb_virtual_server_port" "this" {
  action                                           = var.action
  alt_protocol1                                    = var.alt_protocol1
  alt_protocol2                                    = var.alt_protocol2
  alternate_port                                   = var.alternate_port
  alternate_port_number                            = var.alternate_port_number
  auto                                             = var.auto
  clientip_sticky_nat                              = var.clientip_sticky_nat
  conn_limit                                       = var.conn_limit
  cpu_compute                                      = var.cpu_compute
  def_selection_if_pref_failed                     = var.def_selection_if_pref_failed
  enable_playerid_check                            = var.enable_playerid_check
  eth_fwd                                          = var.eth_fwd
  eth_rev                                          = var.eth_rev
  expand                                           = var.expand
  extended_stats                                   = var.extended_stats
  force_routing_mode                               = var.force_routing_mode
  gslb_enable                                      = var.gslb_enable
  gtp_session_lb                                   = var.gtp_session_lb
  ha_conn_mirror                                   = var.ha_conn_mirror
  ignore_global                                    = var.ignore_global
  ip_map_list                                      = var.ip_map_list
  ipinip                                           = var.ipinip
  l7_hardware_assist                               = var.l7_hardware_assist
  memory_compute                                   = var.memory_compute
  message_switching                                = var.message_switching
  name                                             = var.name
  no_auto_up_on_aflex                              = var.no_auto_up_on_aflex
  no_dest_nat                                      = var.no_dest_nat
  no_logging                                       = var.no_logging
  on_syn                                           = var.on_syn
  optimization_level                               = var.optimization_level
  p_template_sip_shared                            = var.p_template_sip_shared
  persist_type                                     = var.persist_type
  pool                                             = var.pool
  pool_shared                                      = var.pool_shared
  port_number                                      = var.port_number
  port_translation                                 = var.port_translation
  precedence                                       = var.precedence
  protocol                                         = var.protocol
  range                                            = var.range
  rate                                             = var.rate
  redirect_to_https                                = var.redirect_to_https
  req_fail                                         = var.req_fail
  reset                                            = var.reset
  reset_on_server_selection_fail                   = var.reset_on_server_selection_fail
  rtp_sip_call_id_match                            = var.rtp_sip_call_id_match
  scaleout_bucket_count                            = var.scaleout_bucket_count
  scaleout_device_group                            = var.scaleout_device_group
  secs                                             = var.secs
  serv_sel_fail                                    = var.serv_sel_fail
  service_group                                    = var.service_group
  shared_partition_cache_template                  = var.shared_partition_cache_template
  shared_partition_client_ssl_template             = var.shared_partition_client_ssl_template
  shared_partition_connection_reuse_template       = var.shared_partition_connection_reuse_template
  shared_partition_dblb_template                   = var.shared_partition_dblb_template
  shared_partition_diameter_template               = var.shared_partition_diameter_template
  shared_partition_dns_template                    = var.shared_partition_dns_template
  shared_partition_doh_template                    = var.shared_partition_doh_template
  shared_partition_dynamic_service_template        = var.shared_partition_dynamic_service_template
  shared_partition_external_service_template       = var.shared_partition_external_service_template
  shared_partition_fix_template                    = var.shared_partition_fix_template
  shared_partition_http_policy_template            = var.shared_partition_http_policy_template
  shared_partition_http_template                   = var.shared_partition_http_template
  shared_partition_imap_pop3_template              = var.shared_partition_imap_pop3_template
  shared_partition_persist_cookie_template         = var.shared_partition_persist_cookie_template
  shared_partition_persist_destination_ip_template = var.shared_partition_persist_destination_ip_template
  shared_partition_persist_source_ip_template      = var.shared_partition_persist_source_ip_template
  shared_partition_persist_ssl_sid_template        = var.shared_partition_persist_ssl_sid_template
  shared_partition_policy_template                 = var.shared_partition_policy_template
  shared_partition_pool                            = var.shared_partition_pool
  shared_partition_server_ssl_template             = var.shared_partition_server_ssl_template
  shared_partition_smpp_template                   = var.shared_partition_smpp_template
  shared_partition_smtp_template                   = var.shared_partition_smtp_template
  shared_partition_tcp                             = var.shared_partition_tcp
  shared_partition_tcp_proxy_template              = var.shared_partition_tcp_proxy_template
  shared_partition_udp                             = var.shared_partition_udp
  shared_partition_virtual_port_template           = var.shared_partition_virtual_port_template
  skip_rev_hash                                    = var.skip_rev_hash
  snat_on_vip                                      = var.snat_on_vip
  stats_data_action                                = var.stats_data_action
  substitute_source_mac                            = var.substitute_source_mac
  support_http2                                    = var.support_http2
  syn_cookie                                       = var.syn_cookie
  template_cache                                   = var.template_cache
  template_cache_shared                            = var.template_cache_shared
  template_client_ssh                              = var.template_client_ssh
  template_client_ssl                              = var.template_client_ssl
  template_client_ssl_shared                       = var.template_client_ssl_shared
  template_connection_reuse                        = var.template_connection_reuse
  template_connection_reuse_shared                 = var.template_connection_reuse_shared
  template_dblb                                    = var.template_dblb
  template_dblb_shared                             = var.template_dblb_shared
  template_diameter                                = var.template_diameter
  template_diameter_shared                         = var.template_diameter_shared
  template_dns                                     = var.template_dns
  template_dns_shared                              = var.template_dns_shared
  template_doh                                     = var.template_doh
  template_doh_shared                              = var.template_doh_shared
  template_dynamic_service                         = var.template_dynamic_service
  template_dynamic_service_shared                  = var.template_dynamic_service_shared
  template_external_service                        = var.template_external_service
  template_external_service_shared                 = var.template_external_service_shared
  template_file_inspection                         = var.template_file_inspection
  template_fix                                     = var.template_fix
  template_fix_shared                              = var.template_fix_shared
  template_ftp                                     = var.template_ftp
  template_http                                    = var.template_http
  template_http_policy                             = var.template_http_policy
  template_http_policy_shared                      = var.template_http_policy_shared
  template_http_shared                             = var.template_http_shared
  template_imap_pop3                               = var.template_imap_pop3
  template_imap_pop3_shared                        = var.template_imap_pop3_shared
  template_mqtt                                    = var.template_mqtt
  template_persist_cookie                          = var.template_persist_cookie
  template_persist_cookie_shared                   = var.template_persist_cookie_shared
  template_persist_destination_ip                  = var.template_persist_destination_ip
  template_persist_destination_ip_shared           = var.template_persist_destination_ip_shared
  template_persist_source_ip                       = var.template_persist_source_ip
  template_persist_source_ip_shared                = var.template_persist_source_ip_shared
  template_persist_ssl_sid                         = var.template_persist_ssl_sid
  template_persist_ssl_sid_shared                  = var.template_persist_ssl_sid_shared
  template_policy                                  = var.template_policy
  template_policy_shared                           = var.template_policy_shared
  template_reqmod_icap                             = var.template_reqmod_icap
  template_respmod_icap                            = var.template_respmod_icap
  template_scaleout                                = var.template_scaleout
  template_server_ssh                              = var.template_server_ssh
  template_server_ssl                              = var.template_server_ssl
  template_server_ssl_shared                       = var.template_server_ssl_shared
  template_sip                                     = var.template_sip
  template_sip_shared                              = var.template_sip_shared
  template_smpp                                    = var.template_smpp
  template_smpp_shared                             = var.template_smpp_shared
  template_smtp                                    = var.template_smtp
  template_smtp_shared                             = var.template_smtp_shared
  template_ssli                                    = var.template_ssli
  template_tcp                                     = var.template_tcp
  template_tcp_proxy                               = var.template_tcp_proxy
  template_tcp_proxy_client                        = var.template_tcp_proxy_client
  template_tcp_proxy_server                        = var.template_tcp_proxy_server
  template_tcp_proxy_shared                        = var.template_tcp_proxy_shared
  template_tcp_shared                              = var.template_tcp_shared
  template_udp                                     = var.template_udp
  template_udp_shared                              = var.template_udp_shared
  template_virtual_port                            = var.template_virtual_port
  template_virtual_port_shared                     = var.template_virtual_port_shared
  trunk_fwd                                        = var.trunk_fwd
  trunk_rev                                        = var.trunk_rev
  use_alternate_port                               = var.use_alternate_port
  use_cgnv6                                        = var.use_cgnv6
  use_default_if_no_server                         = var.use_default_if_no_server
  use_rcv_hop_for_resp                             = var.use_rcv_hop_for_resp
  user_tag                                         = var.user_tag
  uuid                                             = var.uuid
  view                                             = var.view
  waf_template                                     = var.waf_template
  when_down                                        = var.when_down
  when_down_protocol2                              = var.when_down_protocol2

  dynamic "acl_id_list" {
    for_each = var.acl_id_list
    content {
      acl_id                       = acl_id_list.value["acl_id"]
      acl_id_seq_num               = acl_id_list.value["acl_id_seq_num"]
      acl_id_seq_num_shared        = acl_id_list.value["acl_id_seq_num_shared"]
      acl_id_shared                = acl_id_list.value["acl_id_shared"]
      acl_id_src_nat_pool          = acl_id_list.value["acl_id_src_nat_pool"]
      acl_id_src_nat_pool_shared   = acl_id_list.value["acl_id_src_nat_pool_shared"]
      shared_partition_pool_id     = acl_id_list.value["shared_partition_pool_id"]
      v_acl_id_seq_num             = acl_id_list.value["v_acl_id_seq_num"]
      v_acl_id_seq_num_shared      = acl_id_list.value["v_acl_id_seq_num_shared"]
      v_acl_id_src_nat_pool        = acl_id_list.value["v_acl_id_src_nat_pool"]
      v_acl_id_src_nat_pool_shared = acl_id_list.value["v_acl_id_src_nat_pool_shared"]
      v_shared_partition_pool_id   = acl_id_list.value["v_shared_partition_pool_id"]
    }
  }

  dynamic "acl_name_list" {
    for_each = var.acl_name_list
    content {
      acl_name                       = acl_name_list.value["acl_name"]
      acl_name_seq_num               = acl_name_list.value["acl_name_seq_num"]
      acl_name_seq_num_shared        = acl_name_list.value["acl_name_seq_num_shared"]
      acl_name_shared                = acl_name_list.value["acl_name_shared"]
      acl_name_src_nat_pool          = acl_name_list.value["acl_name_src_nat_pool"]
      acl_name_src_nat_pool_shared   = acl_name_list.value["acl_name_src_nat_pool_shared"]
      shared_partition_pool_name     = acl_name_list.value["shared_partition_pool_name"]
      v_acl_name_seq_num             = acl_name_list.value["v_acl_name_seq_num"]
      v_acl_name_seq_num_shared      = acl_name_list.value["v_acl_name_seq_num_shared"]
      v_acl_name_src_nat_pool        = acl_name_list.value["v_acl_name_src_nat_pool"]
      v_acl_name_src_nat_pool_shared = acl_name_list.value["v_acl_name_src_nat_pool_shared"]
      v_shared_partition_pool_name   = acl_name_list.value["v_shared_partition_pool_name"]
    }
  }

  dynamic "aflex_scripts" {
    for_each = var.aflex_scripts
    content {
      aflex        = aflex_scripts.value["aflex"]
      aflex_shared = aflex_scripts.value["aflex_shared"]
    }
  }

  dynamic "auth_cfg" {
    for_each = var.auth_cfg
    content {
      aaa_policy = auth_cfg.value["aaa_policy"]
    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
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
  value       = thunder_slb_virtual_server_port.this.id
}

output "this" {
  value = thunder_slb_virtual_server_port.this
}
```

[top](#index)