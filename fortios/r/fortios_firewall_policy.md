# fortios_firewall_policy

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
module "fortios_firewall_policy" {
  source = "./modules/fortios/r/fortios_firewall_policy"

  # action - (optional) is a type of string
  action = null
  # anti_replay - (optional) is a type of string
  anti_replay = null
  # application_list - (optional) is a type of string
  application_list = null
  # auth_cert - (optional) is a type of string
  auth_cert = null
  # auth_path - (optional) is a type of string
  auth_path = null
  # auth_redirect_addr - (optional) is a type of string
  auth_redirect_addr = null
  # auto_asic_offload - (optional) is a type of string
  auto_asic_offload = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # block_notification - (optional) is a type of string
  block_notification = null
  # captive_portal_exempt - (optional) is a type of string
  captive_portal_exempt = null
  # capture_packet - (optional) is a type of string
  capture_packet = null
  # cifs_profile - (optional) is a type of string
  cifs_profile = null
  # comments - (optional) is a type of string
  comments = null
  # decrypted_traffic_mirror - (optional) is a type of string
  decrypted_traffic_mirror = null
  # delay_tcp_npu_session - (optional) is a type of string
  delay_tcp_npu_session = null
  # diffserv_forward - (optional) is a type of string
  diffserv_forward = null
  # diffserv_reverse - (optional) is a type of string
  diffserv_reverse = null
  # diffservcode_forward - (optional) is a type of string
  diffservcode_forward = null
  # diffservcode_rev - (optional) is a type of string
  diffservcode_rev = null
  # disclaimer - (optional) is a type of string
  disclaimer = null
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = null
  # dnsfilter_profile - (optional) is a type of string
  dnsfilter_profile = null
  # dsri - (optional) is a type of string
  dsri = null
  # dstaddr_negate - (optional) is a type of string
  dstaddr_negate = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # email_collect - (optional) is a type of string
  email_collect = null
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = null
  # file_filter_profile - (optional) is a type of string
  file_filter_profile = null
  # firewall_session_dirty - (optional) is a type of string
  firewall_session_dirty = null
  # fixedport - (optional) is a type of string
  fixedport = null
  # fsso - (optional) is a type of string
  fsso = null
  # fsso_agent_for_ntlm - (optional) is a type of string
  fsso_agent_for_ntlm = null
  # geoip_anycast - (optional) is a type of string
  geoip_anycast = null
  # geoip_match - (optional) is a type of string
  geoip_match = null
  # global_label - (optional) is a type of string
  global_label = null
  # http_policy_redirect - (optional) is a type of string
  http_policy_redirect = null
  # icap_profile - (optional) is a type of string
  icap_profile = null
  # identity_based_route - (optional) is a type of string
  identity_based_route = null
  # inbound - (optional) is a type of string
  inbound = null
  # inspection_mode - (optional) is a type of string
  inspection_mode = null
  # internet_service - (optional) is a type of string
  internet_service = null
  # internet_service_negate - (optional) is a type of string
  internet_service_negate = null
  # internet_service_src - (optional) is a type of string
  internet_service_src = null
  # internet_service_src_negate - (optional) is a type of string
  internet_service_src_negate = null
  # ippool - (optional) is a type of string
  ippool = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # label - (optional) is a type of string
  label = null
  # learning_mode - (optional) is a type of string
  learning_mode = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = null
  # match_vip - (optional) is a type of string
  match_vip = null
  # match_vip_only - (optional) is a type of string
  match_vip_only = null
  # name - (optional) is a type of string
  name = null
  # nat - (optional) is a type of string
  nat = null
  # natinbound - (optional) is a type of string
  natinbound = null
  # natip - (optional) is a type of string
  natip = null
  # natoutbound - (optional) is a type of string
  natoutbound = null
  # ntlm - (optional) is a type of string
  ntlm = null
  # ntlm_guest - (optional) is a type of string
  ntlm_guest = null
  # outbound - (optional) is a type of string
  outbound = null
  # per_ip_shaper - (optional) is a type of string
  per_ip_shaper = null
  # permit_any_host - (optional) is a type of string
  permit_any_host = null
  # permit_stun_host - (optional) is a type of string
  permit_stun_host = null
  # policyid - (optional) is a type of number
  policyid = null
  # profile_group - (optional) is a type of string
  profile_group = null
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = null
  # profile_type - (optional) is a type of string
  profile_type = null
  # radius_mac_auth_bypass - (optional) is a type of string
  radius_mac_auth_bypass = null
  # redirect_url - (optional) is a type of string
  redirect_url = null
  # replacemsg_override_group - (optional) is a type of string
  replacemsg_override_group = null
  # reputation_direction - (optional) is a type of string
  reputation_direction = null
  # reputation_minimum - (optional) is a type of number
  reputation_minimum = null
  # rsso - (optional) is a type of string
  rsso = null
  # rtp_nat - (optional) is a type of string
  rtp_nat = null
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = null
  # schedule - (optional) is a type of string
  schedule = null
  # schedule_timeout - (optional) is a type of string
  schedule_timeout = null
  # send_deny_packet - (optional) is a type of string
  send_deny_packet = null
  # service_negate - (optional) is a type of string
  service_negate = null
  # session_ttl - (optional) is a type of number
  session_ttl = null
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = null
  # srcaddr_negate - (optional) is a type of string
  srcaddr_negate = null
  # ssh_filter_profile - (optional) is a type of string
  ssh_filter_profile = null
  # ssh_policy_redirect - (optional) is a type of string
  ssh_policy_redirect = null
  # ssl_mirror - (optional) is a type of string
  ssl_mirror = null
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = null
  # status - (optional) is a type of string
  status = null
  # tcp_mss_receiver - (optional) is a type of number
  tcp_mss_receiver = null
  # tcp_mss_sender - (optional) is a type of number
  tcp_mss_sender = null
  # tcp_session_without_syn - (optional) is a type of string
  tcp_session_without_syn = null
  # timeout_send_rst - (optional) is a type of string
  timeout_send_rst = null
  # tos - (optional) is a type of string
  tos = null
  # tos_mask - (optional) is a type of string
  tos_mask = null
  # tos_negate - (optional) is a type of string
  tos_negate = null
  # traffic_shaper - (optional) is a type of string
  traffic_shaper = null
  # traffic_shaper_reverse - (optional) is a type of string
  traffic_shaper_reverse = null
  # utm_status - (optional) is a type of string
  utm_status = null
  # uuid - (optional) is a type of string
  uuid = null
  # vlan_cos_fwd - (optional) is a type of number
  vlan_cos_fwd = null
  # vlan_cos_rev - (optional) is a type of number
  vlan_cos_rev = null
  # vlan_filter - (optional) is a type of string
  vlan_filter = null
  # voip_profile - (optional) is a type of string
  voip_profile = null
  # vpntunnel - (optional) is a type of string
  vpntunnel = null
  # waf_profile - (optional) is a type of string
  waf_profile = null
  # wanopt - (optional) is a type of string
  wanopt = null
  # wanopt_detection - (optional) is a type of string
  wanopt_detection = null
  # wanopt_passive_opt - (optional) is a type of string
  wanopt_passive_opt = null
  # wanopt_peer - (optional) is a type of string
  wanopt_peer = null
  # wanopt_profile - (optional) is a type of string
  wanopt_profile = null
  # wccp - (optional) is a type of string
  wccp = null
  # webcache - (optional) is a type of string
  webcache = null
  # webcache_https - (optional) is a type of string
  webcache_https = null
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null
  # webproxy_forward_server - (optional) is a type of string
  webproxy_forward_server = null
  # webproxy_profile - (optional) is a type of string
  webproxy_profile = null
  # wsso - (optional) is a type of string
  wsso = null

  app_category = [{
    id = null
  }]

  app_group = [{
    name = null
  }]

  application = [{
    id = null
  }]

  custom_log_fields = [{
    field_id = null
  }]

  devices = [{
    name = null
  }]

  dstaddr = [{
    name = null
  }]

  dstaddr6 = [{
    name = null
  }]

  dstintf = [{
    name = null
  }]

  fsso_groups = [{
    name = null
  }]

  groups = [{
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

  internet_service_src_custom = [{
    name = null
  }]

  internet_service_src_custom_group = [{
    name = null
  }]

  internet_service_src_group = [{
    name = null
  }]

  internet_service_src_id = [{
    id = null
  }]

  internet_service_src_name = [{
    name = null
  }]

  ntlm_enabled_browsers = [{
    user_agent_string = null
  }]

  poolname = [{
    name = null
  }]

  poolname6 = [{
    name = null
  }]

  rtp_addr = [{
    name = null
  }]

  service = [{
    name = null
  }]

  src_vendor_mac = [{
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

  ssl_mirror_intf = [{
    name = null
  }]

  url_category = [{
    id = null
  }]

  users = [{
    name = null
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

variable "anti_replay" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_redirect_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_asic_offload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_notification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_exempt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capture_packet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cifs_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "decrypted_traffic_mirror" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delay_tcp_npu_session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffserv_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffserv_reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode_rev" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disclaimer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dlp_sensor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnsfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dsri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dstaddr_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_collect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "emailfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_filter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_session_dirty" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fixedport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsso" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsso_agent_for_ntlm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geoip_anycast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geoip_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_policy_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icap_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_based_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inbound" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_src" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_src_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ippool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_sensor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "learning_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logtraffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logtraffic_start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_vip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_vip_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "natinbound" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "natip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "natoutbound" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntlm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ntlm_guest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outbound" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_ip_shaper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permit_any_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permit_stun_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policyid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "profile_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_protocol_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_mac_auth_bypass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redirect_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacemsg_override_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reputation_direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reputation_minimum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rsso" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rtp_nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_botnet_connections" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "send_deny_packet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spamfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "srcaddr_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_filter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_policy_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_mirror" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_ssh_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_mss_receiver" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_mss_sender" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_session_without_syn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout_send_rst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos_mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_shaper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_shaper_reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "utm_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_cos_fwd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vlan_cos_rev" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vlan_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voip_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpntunnel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "waf_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanopt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanopt_detection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanopt_passive_opt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanopt_peer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanopt_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wccp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webcache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webcache_https" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webproxy_forward_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webproxy_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wsso" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "app_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "application" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "custom_log_fields" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      field_id = string
    }
  ))
  default = []
}

variable "devices" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "dstaddr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "dstaddr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "dstintf" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "fsso_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_custom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_custom_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_id" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "internet_service_name" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_custom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_custom_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_id" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "internet_service_src_name" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "ntlm_enabled_browsers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      user_agent_string = string
    }
  ))
  default = []
}

variable "poolname" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "poolname6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "rtp_addr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "src_vendor_mac" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "srcaddr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcaddr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcintf" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "ssl_mirror_intf" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "url_category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "users" {
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
resource "fortios_firewall_policy" "this" {
  # action - (optional) is a type of string
  action = var.action
  # anti_replay - (optional) is a type of string
  anti_replay = var.anti_replay
  # application_list - (optional) is a type of string
  application_list = var.application_list
  # auth_cert - (optional) is a type of string
  auth_cert = var.auth_cert
  # auth_path - (optional) is a type of string
  auth_path = var.auth_path
  # auth_redirect_addr - (optional) is a type of string
  auth_redirect_addr = var.auth_redirect_addr
  # auto_asic_offload - (optional) is a type of string
  auto_asic_offload = var.auto_asic_offload
  # av_profile - (optional) is a type of string
  av_profile = var.av_profile
  # block_notification - (optional) is a type of string
  block_notification = var.block_notification
  # captive_portal_exempt - (optional) is a type of string
  captive_portal_exempt = var.captive_portal_exempt
  # capture_packet - (optional) is a type of string
  capture_packet = var.capture_packet
  # cifs_profile - (optional) is a type of string
  cifs_profile = var.cifs_profile
  # comments - (optional) is a type of string
  comments = var.comments
  # decrypted_traffic_mirror - (optional) is a type of string
  decrypted_traffic_mirror = var.decrypted_traffic_mirror
  # delay_tcp_npu_session - (optional) is a type of string
  delay_tcp_npu_session = var.delay_tcp_npu_session
  # diffserv_forward - (optional) is a type of string
  diffserv_forward = var.diffserv_forward
  # diffserv_reverse - (optional) is a type of string
  diffserv_reverse = var.diffserv_reverse
  # diffservcode_forward - (optional) is a type of string
  diffservcode_forward = var.diffservcode_forward
  # diffservcode_rev - (optional) is a type of string
  diffservcode_rev = var.diffservcode_rev
  # disclaimer - (optional) is a type of string
  disclaimer = var.disclaimer
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = var.dlp_sensor
  # dnsfilter_profile - (optional) is a type of string
  dnsfilter_profile = var.dnsfilter_profile
  # dsri - (optional) is a type of string
  dsri = var.dsri
  # dstaddr_negate - (optional) is a type of string
  dstaddr_negate = var.dstaddr_negate
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # email_collect - (optional) is a type of string
  email_collect = var.email_collect
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = var.emailfilter_profile
  # file_filter_profile - (optional) is a type of string
  file_filter_profile = var.file_filter_profile
  # firewall_session_dirty - (optional) is a type of string
  firewall_session_dirty = var.firewall_session_dirty
  # fixedport - (optional) is a type of string
  fixedport = var.fixedport
  # fsso - (optional) is a type of string
  fsso = var.fsso
  # fsso_agent_for_ntlm - (optional) is a type of string
  fsso_agent_for_ntlm = var.fsso_agent_for_ntlm
  # geoip_anycast - (optional) is a type of string
  geoip_anycast = var.geoip_anycast
  # geoip_match - (optional) is a type of string
  geoip_match = var.geoip_match
  # global_label - (optional) is a type of string
  global_label = var.global_label
  # http_policy_redirect - (optional) is a type of string
  http_policy_redirect = var.http_policy_redirect
  # icap_profile - (optional) is a type of string
  icap_profile = var.icap_profile
  # identity_based_route - (optional) is a type of string
  identity_based_route = var.identity_based_route
  # inbound - (optional) is a type of string
  inbound = var.inbound
  # inspection_mode - (optional) is a type of string
  inspection_mode = var.inspection_mode
  # internet_service - (optional) is a type of string
  internet_service = var.internet_service
  # internet_service_negate - (optional) is a type of string
  internet_service_negate = var.internet_service_negate
  # internet_service_src - (optional) is a type of string
  internet_service_src = var.internet_service_src
  # internet_service_src_negate - (optional) is a type of string
  internet_service_src_negate = var.internet_service_src_negate
  # ippool - (optional) is a type of string
  ippool = var.ippool
  # ips_sensor - (optional) is a type of string
  ips_sensor = var.ips_sensor
  # label - (optional) is a type of string
  label = var.label
  # learning_mode - (optional) is a type of string
  learning_mode = var.learning_mode
  # logtraffic - (optional) is a type of string
  logtraffic = var.logtraffic
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = var.logtraffic_start
  # match_vip - (optional) is a type of string
  match_vip = var.match_vip
  # match_vip_only - (optional) is a type of string
  match_vip_only = var.match_vip_only
  # name - (optional) is a type of string
  name = var.name
  # nat - (optional) is a type of string
  nat = var.nat
  # natinbound - (optional) is a type of string
  natinbound = var.natinbound
  # natip - (optional) is a type of string
  natip = var.natip
  # natoutbound - (optional) is a type of string
  natoutbound = var.natoutbound
  # ntlm - (optional) is a type of string
  ntlm = var.ntlm
  # ntlm_guest - (optional) is a type of string
  ntlm_guest = var.ntlm_guest
  # outbound - (optional) is a type of string
  outbound = var.outbound
  # per_ip_shaper - (optional) is a type of string
  per_ip_shaper = var.per_ip_shaper
  # permit_any_host - (optional) is a type of string
  permit_any_host = var.permit_any_host
  # permit_stun_host - (optional) is a type of string
  permit_stun_host = var.permit_stun_host
  # policyid - (optional) is a type of number
  policyid = var.policyid
  # profile_group - (optional) is a type of string
  profile_group = var.profile_group
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = var.profile_protocol_options
  # profile_type - (optional) is a type of string
  profile_type = var.profile_type
  # radius_mac_auth_bypass - (optional) is a type of string
  radius_mac_auth_bypass = var.radius_mac_auth_bypass
  # redirect_url - (optional) is a type of string
  redirect_url = var.redirect_url
  # replacemsg_override_group - (optional) is a type of string
  replacemsg_override_group = var.replacemsg_override_group
  # reputation_direction - (optional) is a type of string
  reputation_direction = var.reputation_direction
  # reputation_minimum - (optional) is a type of number
  reputation_minimum = var.reputation_minimum
  # rsso - (optional) is a type of string
  rsso = var.rsso
  # rtp_nat - (optional) is a type of string
  rtp_nat = var.rtp_nat
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = var.scan_botnet_connections
  # schedule - (optional) is a type of string
  schedule = var.schedule
  # schedule_timeout - (optional) is a type of string
  schedule_timeout = var.schedule_timeout
  # send_deny_packet - (optional) is a type of string
  send_deny_packet = var.send_deny_packet
  # service_negate - (optional) is a type of string
  service_negate = var.service_negate
  # session_ttl - (optional) is a type of number
  session_ttl = var.session_ttl
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = var.spamfilter_profile
  # srcaddr_negate - (optional) is a type of string
  srcaddr_negate = var.srcaddr_negate
  # ssh_filter_profile - (optional) is a type of string
  ssh_filter_profile = var.ssh_filter_profile
  # ssh_policy_redirect - (optional) is a type of string
  ssh_policy_redirect = var.ssh_policy_redirect
  # ssl_mirror - (optional) is a type of string
  ssl_mirror = var.ssl_mirror
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = var.ssl_ssh_profile
  # status - (optional) is a type of string
  status = var.status
  # tcp_mss_receiver - (optional) is a type of number
  tcp_mss_receiver = var.tcp_mss_receiver
  # tcp_mss_sender - (optional) is a type of number
  tcp_mss_sender = var.tcp_mss_sender
  # tcp_session_without_syn - (optional) is a type of string
  tcp_session_without_syn = var.tcp_session_without_syn
  # timeout_send_rst - (optional) is a type of string
  timeout_send_rst = var.timeout_send_rst
  # tos - (optional) is a type of string
  tos = var.tos
  # tos_mask - (optional) is a type of string
  tos_mask = var.tos_mask
  # tos_negate - (optional) is a type of string
  tos_negate = var.tos_negate
  # traffic_shaper - (optional) is a type of string
  traffic_shaper = var.traffic_shaper
  # traffic_shaper_reverse - (optional) is a type of string
  traffic_shaper_reverse = var.traffic_shaper_reverse
  # utm_status - (optional) is a type of string
  utm_status = var.utm_status
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vlan_cos_fwd - (optional) is a type of number
  vlan_cos_fwd = var.vlan_cos_fwd
  # vlan_cos_rev - (optional) is a type of number
  vlan_cos_rev = var.vlan_cos_rev
  # vlan_filter - (optional) is a type of string
  vlan_filter = var.vlan_filter
  # voip_profile - (optional) is a type of string
  voip_profile = var.voip_profile
  # vpntunnel - (optional) is a type of string
  vpntunnel = var.vpntunnel
  # waf_profile - (optional) is a type of string
  waf_profile = var.waf_profile
  # wanopt - (optional) is a type of string
  wanopt = var.wanopt
  # wanopt_detection - (optional) is a type of string
  wanopt_detection = var.wanopt_detection
  # wanopt_passive_opt - (optional) is a type of string
  wanopt_passive_opt = var.wanopt_passive_opt
  # wanopt_peer - (optional) is a type of string
  wanopt_peer = var.wanopt_peer
  # wanopt_profile - (optional) is a type of string
  wanopt_profile = var.wanopt_profile
  # wccp - (optional) is a type of string
  wccp = var.wccp
  # webcache - (optional) is a type of string
  webcache = var.webcache
  # webcache_https - (optional) is a type of string
  webcache_https = var.webcache_https
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = var.webfilter_profile
  # webproxy_forward_server - (optional) is a type of string
  webproxy_forward_server = var.webproxy_forward_server
  # webproxy_profile - (optional) is a type of string
  webproxy_profile = var.webproxy_profile
  # wsso - (optional) is a type of string
  wsso = var.wsso

  dynamic "app_category" {
    for_each = var.app_category
    content {
      # id - (optional) is a type of number
      id = app_category.value["id"]
    }
  }

  dynamic "app_group" {
    for_each = var.app_group
    content {
      # name - (optional) is a type of string
      name = app_group.value["name"]
    }
  }

  dynamic "application" {
    for_each = var.application
    content {
      # id - (optional) is a type of number
      id = application.value["id"]
    }
  }

  dynamic "custom_log_fields" {
    for_each = var.custom_log_fields
    content {
      # field_id - (optional) is a type of string
      field_id = custom_log_fields.value["field_id"]
    }
  }

  dynamic "devices" {
    for_each = var.devices
    content {
      # name - (optional) is a type of string
      name = devices.value["name"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      # name - (optional) is a type of string
      name = dstaddr.value["name"]
    }
  }

  dynamic "dstaddr6" {
    for_each = var.dstaddr6
    content {
      # name - (optional) is a type of string
      name = dstaddr6.value["name"]
    }
  }

  dynamic "dstintf" {
    for_each = var.dstintf
    content {
      # name - (optional) is a type of string
      name = dstintf.value["name"]
    }
  }

  dynamic "fsso_groups" {
    for_each = var.fsso_groups
    content {
      # name - (optional) is a type of string
      name = fsso_groups.value["name"]
    }
  }

  dynamic "groups" {
    for_each = var.groups
    content {
      # name - (optional) is a type of string
      name = groups.value["name"]
    }
  }

  dynamic "internet_service_custom" {
    for_each = var.internet_service_custom
    content {
      # name - (optional) is a type of string
      name = internet_service_custom.value["name"]
    }
  }

  dynamic "internet_service_custom_group" {
    for_each = var.internet_service_custom_group
    content {
      # name - (optional) is a type of string
      name = internet_service_custom_group.value["name"]
    }
  }

  dynamic "internet_service_group" {
    for_each = var.internet_service_group
    content {
      # name - (optional) is a type of string
      name = internet_service_group.value["name"]
    }
  }

  dynamic "internet_service_id" {
    for_each = var.internet_service_id
    content {
      # id - (optional) is a type of number
      id = internet_service_id.value["id"]
    }
  }

  dynamic "internet_service_name" {
    for_each = var.internet_service_name
    content {
      # name - (optional) is a type of string
      name = internet_service_name.value["name"]
    }
  }

  dynamic "internet_service_src_custom" {
    for_each = var.internet_service_src_custom
    content {
      # name - (optional) is a type of string
      name = internet_service_src_custom.value["name"]
    }
  }

  dynamic "internet_service_src_custom_group" {
    for_each = var.internet_service_src_custom_group
    content {
      # name - (optional) is a type of string
      name = internet_service_src_custom_group.value["name"]
    }
  }

  dynamic "internet_service_src_group" {
    for_each = var.internet_service_src_group
    content {
      # name - (optional) is a type of string
      name = internet_service_src_group.value["name"]
    }
  }

  dynamic "internet_service_src_id" {
    for_each = var.internet_service_src_id
    content {
      # id - (optional) is a type of number
      id = internet_service_src_id.value["id"]
    }
  }

  dynamic "internet_service_src_name" {
    for_each = var.internet_service_src_name
    content {
      # name - (optional) is a type of string
      name = internet_service_src_name.value["name"]
    }
  }

  dynamic "ntlm_enabled_browsers" {
    for_each = var.ntlm_enabled_browsers
    content {
      # user_agent_string - (optional) is a type of string
      user_agent_string = ntlm_enabled_browsers.value["user_agent_string"]
    }
  }

  dynamic "poolname" {
    for_each = var.poolname
    content {
      # name - (optional) is a type of string
      name = poolname.value["name"]
    }
  }

  dynamic "poolname6" {
    for_each = var.poolname6
    content {
      # name - (optional) is a type of string
      name = poolname6.value["name"]
    }
  }

  dynamic "rtp_addr" {
    for_each = var.rtp_addr
    content {
      # name - (optional) is a type of string
      name = rtp_addr.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      # name - (optional) is a type of string
      name = service.value["name"]
    }
  }

  dynamic "src_vendor_mac" {
    for_each = var.src_vendor_mac
    content {
      # id - (optional) is a type of number
      id = src_vendor_mac.value["id"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      # name - (optional) is a type of string
      name = srcaddr.value["name"]
    }
  }

  dynamic "srcaddr6" {
    for_each = var.srcaddr6
    content {
      # name - (optional) is a type of string
      name = srcaddr6.value["name"]
    }
  }

  dynamic "srcintf" {
    for_each = var.srcintf
    content {
      # name - (optional) is a type of string
      name = srcintf.value["name"]
    }
  }

  dynamic "ssl_mirror_intf" {
    for_each = var.ssl_mirror_intf
    content {
      # name - (optional) is a type of string
      name = ssl_mirror_intf.value["name"]
    }
  }

  dynamic "url_category" {
    for_each = var.url_category
    content {
      # id - (optional) is a type of number
      id = url_category.value["id"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
      # name - (optional) is a type of string
      name = users.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.action
}

output "anti_replay" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.anti_replay
}

output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.application_list
}

output "auth_cert" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.auth_cert
}

output "auth_path" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.auth_path
}

output "auth_redirect_addr" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.auth_redirect_addr
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.auto_asic_offload
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.av_profile
}

output "block_notification" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.block_notification
}

output "captive_portal_exempt" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.captive_portal_exempt
}

output "capture_packet" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.capture_packet
}

output "cifs_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.cifs_profile
}

output "decrypted_traffic_mirror" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.decrypted_traffic_mirror
}

output "delay_tcp_npu_session" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.delay_tcp_npu_session
}

output "diffserv_forward" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.diffservcode_rev
}

output "disclaimer" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.disclaimer
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.dnsfilter_profile
}

output "dsri" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.dsri
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.dstaddr_negate
}

output "email_collect" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.email_collect
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.emailfilter_profile
}

output "file_filter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.file_filter_profile
}

output "firewall_session_dirty" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.firewall_session_dirty
}

output "fixedport" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.fixedport
}

output "fsso" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.fsso
}

output "fsso_agent_for_ntlm" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.fsso_agent_for_ntlm
}

output "geoip_anycast" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.geoip_anycast
}

output "geoip_match" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.geoip_match
}

output "global_label" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.global_label
}

output "http_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.http_policy_redirect
}

output "icap_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.id
}

output "identity_based_route" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.identity_based_route
}

output "inbound" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.inbound
}

output "inspection_mode" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.inspection_mode
}

output "internet_service" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.internet_service
}

output "internet_service_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.internet_service_negate
}

output "internet_service_src" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.internet_service_src
}

output "internet_service_src_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.internet_service_src_negate
}

output "ippool" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ips_sensor
}

output "label" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.label
}

output "learning_mode" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.learning_mode
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.logtraffic_start
}

output "match_vip" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.match_vip
}

output "match_vip_only" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.match_vip_only
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.name
}

output "nat" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.nat
}

output "natinbound" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.natinbound
}

output "natip" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.natip
}

output "natoutbound" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.natoutbound
}

output "ntlm" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ntlm
}

output "ntlm_guest" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ntlm_guest
}

output "outbound" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.outbound
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.per_ip_shaper
}

output "permit_any_host" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.permit_any_host
}

output "permit_stun_host" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.permit_stun_host
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.policyid
}

output "profile_group" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.profile_type
}

output "radius_mac_auth_bypass" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.radius_mac_auth_bypass
}

output "redirect_url" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.redirect_url
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.replacemsg_override_group
}

output "reputation_direction" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.reputation_direction
}

output "reputation_minimum" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.reputation_minimum
}

output "rsso" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.rsso
}

output "rtp_nat" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.rtp_nat
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.scan_botnet_connections
}

output "schedule_timeout" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.schedule_timeout
}

output "send_deny_packet" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.send_deny_packet
}

output "service_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.spamfilter_profile
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.srcaddr_negate
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ssh_policy_redirect
}

output "ssl_mirror" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ssl_mirror
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.tcp_mss_sender
}

output "tcp_session_without_syn" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.tcp_session_without_syn
}

output "timeout_send_rst" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.timeout_send_rst
}

output "tos" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.tos_mask
}

output "tos_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.tos_negate
}

output "traffic_shaper" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.traffic_shaper_reverse
}

output "utm_status" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.uuid
}

output "vlan_cos_fwd" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.vlan_cos_fwd
}

output "vlan_cos_rev" {
  description = "returns a number"
  value       = fortios_firewall_policy.this.vlan_cos_rev
}

output "vlan_filter" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.vlan_filter
}

output "voip_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.voip_profile
}

output "vpntunnel" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.vpntunnel
}

output "waf_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.waf_profile
}

output "wanopt" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wanopt
}

output "wanopt_detection" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wanopt_detection
}

output "wanopt_passive_opt" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wanopt_passive_opt
}

output "wanopt_peer" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wanopt_peer
}

output "wanopt_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wanopt_profile
}

output "wccp" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wccp
}

output "webcache" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.webproxy_profile
}

output "wsso" {
  description = "returns a string"
  value       = fortios_firewall_policy.this.wsso
}

output "this" {
  value = fortios_firewall_policy.this
}
```

[top](#index)