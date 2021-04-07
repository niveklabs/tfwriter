# fortios_firewall_policy

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
module "fortios_firewall_policy" {
  source = "./modules/fortios/d/fortios_firewall_policy"

  # policyid - (required) is a type of number
  policyid = null
}
```

[top](#index)

### Variables

```terraform
variable "policyid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_firewall_policy" "this" {
  # policyid - (required) is a type of number
  policyid = var.policyid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.action
}

output "anti_replay" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.anti_replay
}

output "app_category" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.app_category
}

output "app_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.app_group
}

output "application" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.application
}

output "application_list" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.application_list
}

output "auth_cert" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.auth_cert
}

output "auth_path" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.auth_path
}

output "auth_redirect_addr" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.auth_redirect_addr
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.auto_asic_offload
}

output "av_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.av_profile
}

output "block_notification" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.block_notification
}

output "captive_portal_exempt" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.captive_portal_exempt
}

output "capture_packet" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.capture_packet
}

output "cifs_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.cifs_profile
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.comments
}

output "custom_log_fields" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.custom_log_fields
}

output "decrypted_traffic_mirror" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.decrypted_traffic_mirror
}

output "delay_tcp_npu_session" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.delay_tcp_npu_session
}

output "devices" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.devices
}

output "diffserv_forward" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.diffservcode_rev
}

output "disclaimer" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.disclaimer
}

output "dlp_sensor" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.dnsfilter_profile
}

output "dsri" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.dsri
}

output "dstaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.dstaddr
}

output "dstaddr6" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.dstaddr6
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.dstaddr_negate
}

output "dstintf" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.dstintf
}

output "email_collect" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.email_collect
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.emailfilter_profile
}

output "file_filter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.file_filter_profile
}

output "firewall_session_dirty" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.firewall_session_dirty
}

output "fixedport" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.fixedport
}

output "fsso" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.fsso
}

output "fsso_agent_for_ntlm" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.fsso_agent_for_ntlm
}

output "fsso_groups" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.fsso_groups
}

output "geoip_anycast" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.geoip_anycast
}

output "geoip_match" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.geoip_match
}

output "global_label" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.global_label
}

output "groups" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.groups
}

output "http_policy_redirect" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.http_policy_redirect
}

output "icap_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.id
}

output "identity_based_route" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.identity_based_route
}

output "inbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.inbound
}

output "inspection_mode" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.inspection_mode
}

output "internet_service" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.internet_service
}

output "internet_service_custom" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_custom
}

output "internet_service_custom_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_custom_group
}

output "internet_service_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_group
}

output "internet_service_id" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_id
}

output "internet_service_name" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_name
}

output "internet_service_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.internet_service_negate
}

output "internet_service_src" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.internet_service_src
}

output "internet_service_src_custom" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_src_custom
}

output "internet_service_src_custom_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_src_custom_group
}

output "internet_service_src_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_src_group
}

output "internet_service_src_id" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_src_id
}

output "internet_service_src_name" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.internet_service_src_name
}

output "internet_service_src_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.internet_service_src_negate
}

output "ippool" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ips_sensor
}

output "label" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.label
}

output "learning_mode" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.learning_mode
}

output "logtraffic" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.logtraffic_start
}

output "match_vip" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.match_vip
}

output "match_vip_only" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.match_vip_only
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.name
}

output "nat" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.nat
}

output "natinbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.natinbound
}

output "natip" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.natip
}

output "natoutbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.natoutbound
}

output "ntlm" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ntlm
}

output "ntlm_enabled_browsers" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.ntlm_enabled_browsers
}

output "ntlm_guest" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ntlm_guest
}

output "outbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.outbound
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.per_ip_shaper
}

output "permit_any_host" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.permit_any_host
}

output "permit_stun_host" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.permit_stun_host
}

output "poolname" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.poolname
}

output "poolname6" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.poolname6
}

output "profile_group" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.profile_type
}

output "radius_mac_auth_bypass" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.radius_mac_auth_bypass
}

output "redirect_url" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.redirect_url
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.replacemsg_override_group
}

output "reputation_direction" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.reputation_direction
}

output "reputation_minimum" {
  description = "returns a number"
  value       = data.fortios_firewall_policy.this.reputation_minimum
}

output "rsso" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.rsso
}

output "rtp_addr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.rtp_addr
}

output "rtp_nat" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.rtp_nat
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.scan_botnet_connections
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.schedule
}

output "schedule_timeout" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.schedule_timeout
}

output "send_deny_packet" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.send_deny_packet
}

output "service" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.service
}

output "service_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = data.fortios_firewall_policy.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.spamfilter_profile
}

output "src_vendor_mac" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.src_vendor_mac
}

output "srcaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.srcaddr
}

output "srcaddr6" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.srcaddr6
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.srcaddr_negate
}

output "srcintf" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.srcintf
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ssh_policy_redirect
}

output "ssl_mirror" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ssl_mirror
}

output "ssl_mirror_intf" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.ssl_mirror_intf
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = data.fortios_firewall_policy.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = data.fortios_firewall_policy.this.tcp_mss_sender
}

output "tcp_session_without_syn" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.tcp_session_without_syn
}

output "timeout_send_rst" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.timeout_send_rst
}

output "tos" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.tos_mask
}

output "tos_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.tos_negate
}

output "traffic_shaper" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.traffic_shaper_reverse
}

output "url_category" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.url_category
}

output "users" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy.this.users
}

output "utm_status" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.uuid
}

output "vlan_cos_fwd" {
  description = "returns a number"
  value       = data.fortios_firewall_policy.this.vlan_cos_fwd
}

output "vlan_cos_rev" {
  description = "returns a number"
  value       = data.fortios_firewall_policy.this.vlan_cos_rev
}

output "vlan_filter" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.vlan_filter
}

output "voip_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.voip_profile
}

output "vpntunnel" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.vpntunnel
}

output "waf_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.waf_profile
}

output "wanopt" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wanopt
}

output "wanopt_detection" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wanopt_detection
}

output "wanopt_passive_opt" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wanopt_passive_opt
}

output "wanopt_peer" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wanopt_peer
}

output "wanopt_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wanopt_profile
}

output "wccp" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wccp
}

output "webcache" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.webproxy_profile
}

output "wsso" {
  description = "returns a string"
  value       = data.fortios_firewall_policy.this.wsso
}

output "this" {
  value = fortios_firewall_policy.this
}
```

[top](#index)