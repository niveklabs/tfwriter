# fortios_firewallconsolidated_policy

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
module "fortios_firewallconsolidated_policy" {
  source = "./modules/fortios/d/fortios_firewallconsolidated_policy"

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
data "fortios_firewallconsolidated_policy" "this" {
  # policyid - (required) is a type of number
  policyid = var.policyid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.action
}

output "app_category" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.app_category
}

output "app_group" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.app_group
}

output "application" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.application
}

output "application_list" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.application_list
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.auto_asic_offload
}

output "av_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.av_profile
}

output "captive_portal_exempt" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.captive_portal_exempt
}

output "cifs_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.cifs_profile
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.comments
}

output "diffserv_forward" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.diffservcode_rev
}

output "dlp_sensor" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.dnsfilter_profile
}

output "dstaddr4" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.dstaddr4
}

output "dstaddr6" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.dstaddr6
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.dstaddr_negate
}

output "dstintf" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.dstintf
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.emailfilter_profile
}

output "fixedport" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.fixedport
}

output "fsso_groups" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.fsso_groups
}

output "groups" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.groups
}

output "http_policy_redirect" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.http_policy_redirect
}

output "icap_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.id
}

output "inbound" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.inbound
}

output "inspection_mode" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.inspection_mode
}

output "internet_service" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service
}

output "internet_service_custom" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_custom
}

output "internet_service_custom_group" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_custom_group
}

output "internet_service_group" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_group
}

output "internet_service_id" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_id
}

output "internet_service_name" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_name
}

output "internet_service_negate" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_negate
}

output "internet_service_src" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src
}

output "internet_service_src_custom" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src_custom
}

output "internet_service_src_custom_group" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src_custom_group
}

output "internet_service_src_group" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src_group
}

output "internet_service_src_id" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src_id
}

output "internet_service_src_name" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src_name
}

output "internet_service_src_negate" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.internet_service_src_negate
}

output "ippool" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.ips_sensor
}

output "logtraffic" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.name
}

output "nat" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.nat
}

output "outbound" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.outbound
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.per_ip_shaper
}

output "poolname4" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.poolname4
}

output "poolname6" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.poolname6
}

output "profile_group" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.profile_type
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.schedule
}

output "service" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.service
}

output "service_negate" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = data.fortios_firewallconsolidated_policy.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.spamfilter_profile
}

output "srcaddr4" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.srcaddr4
}

output "srcaddr6" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.srcaddr6
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.srcaddr_negate
}

output "srcintf" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.srcintf
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.ssh_policy_redirect
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = data.fortios_firewallconsolidated_policy.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = data.fortios_firewallconsolidated_policy.this.tcp_mss_sender
}

output "traffic_shaper" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.traffic_shaper_reverse
}

output "url_category" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.url_category
}

output "users" {
  description = "returns a list of object"
  value       = data.fortios_firewallconsolidated_policy.this.users
}

output "utm_status" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.uuid
}

output "voip_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.voip_profile
}

output "vpntunnel" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.vpntunnel
}

output "waf_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.waf_profile
}

output "wanopt" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.wanopt
}

output "wanopt_detection" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.wanopt_detection
}

output "wanopt_passive_opt" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.wanopt_passive_opt
}

output "wanopt_peer" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.wanopt_peer
}

output "wanopt_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.wanopt_profile
}

output "webcache" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = data.fortios_firewallconsolidated_policy.this.webproxy_profile
}

output "this" {
  value = fortios_firewallconsolidated_policy.this
}
```

[top](#index)