# fortios_firewall_policy6

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
module "fortios_firewall_policy6" {
  source = "./modules/fortios/d/fortios_firewall_policy6"

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
data "fortios_firewall_policy6" "this" {
  # policyid - (required) is a type of number
  policyid = var.policyid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.action
}

output "anti_replay" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.anti_replay
}

output "app_category" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.app_category
}

output "app_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.app_group
}

output "application" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.application
}

output "application_list" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.application_list
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.auto_asic_offload
}

output "av_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.av_profile
}

output "cifs_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.cifs_profile
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.comments
}

output "custom_log_fields" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.custom_log_fields
}

output "decrypted_traffic_mirror" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.decrypted_traffic_mirror
}

output "devices" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.devices
}

output "diffserv_forward" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.diffservcode_rev
}

output "dlp_sensor" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.dnsfilter_profile
}

output "dsri" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.dsri
}

output "dstaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.dstaddr
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.dstaddr_negate
}

output "dstintf" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.dstintf
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.emailfilter_profile
}

output "firewall_session_dirty" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.firewall_session_dirty
}

output "fixedport" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.fixedport
}

output "fsso_groups" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.fsso_groups
}

output "global_label" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.global_label
}

output "groups" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.groups
}

output "http_policy_redirect" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.http_policy_redirect
}

output "icap_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.id
}

output "inbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.inbound
}

output "inspection_mode" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.inspection_mode
}

output "ippool" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.ips_sensor
}

output "label" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.label
}

output "logtraffic" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.name
}

output "nat" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.nat
}

output "natinbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.natinbound
}

output "natoutbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.natoutbound
}

output "outbound" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.outbound
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.per_ip_shaper
}

output "poolname" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.poolname
}

output "profile_group" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.profile_type
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.replacemsg_override_group
}

output "rsso" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.rsso
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.schedule
}

output "send_deny_packet" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.send_deny_packet
}

output "service" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.service
}

output "service_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = data.fortios_firewall_policy6.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.spamfilter_profile
}

output "srcaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.srcaddr
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.srcaddr_negate
}

output "srcintf" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.srcintf
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.ssh_policy_redirect
}

output "ssl_mirror" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.ssl_mirror
}

output "ssl_mirror_intf" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.ssl_mirror_intf
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = data.fortios_firewall_policy6.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = data.fortios_firewall_policy6.this.tcp_mss_sender
}

output "tcp_session_without_syn" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.tcp_session_without_syn
}

output "timeout_send_rst" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.timeout_send_rst
}

output "tos" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.tos_mask
}

output "tos_negate" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.tos_negate
}

output "traffic_shaper" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.traffic_shaper_reverse
}

output "url_category" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.url_category
}

output "users" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy6.this.users
}

output "utm_status" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.uuid
}

output "vlan_cos_fwd" {
  description = "returns a number"
  value       = data.fortios_firewall_policy6.this.vlan_cos_fwd
}

output "vlan_cos_rev" {
  description = "returns a number"
  value       = data.fortios_firewall_policy6.this.vlan_cos_rev
}

output "vlan_filter" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.vlan_filter
}

output "voip_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.voip_profile
}

output "vpntunnel" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.vpntunnel
}

output "waf_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.waf_profile
}

output "webcache" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = data.fortios_firewall_policy6.this.webproxy_profile
}

output "this" {
  value = fortios_firewall_policy6.this
}
```

[top](#index)