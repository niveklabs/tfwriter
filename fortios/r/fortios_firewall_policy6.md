# fortios_firewall_policy6

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
module "fortios_firewall_policy6" {
  source = "./modules/fortios/r/fortios_firewall_policy6"

  # action - (optional) is a type of string
  action = null
  # anti_replay - (optional) is a type of string
  anti_replay = null
  # application_list - (optional) is a type of string
  application_list = null
  # auto_asic_offload - (optional) is a type of string
  auto_asic_offload = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # cifs_profile - (optional) is a type of string
  cifs_profile = null
  # comments - (optional) is a type of string
  comments = null
  # decrypted_traffic_mirror - (optional) is a type of string
  decrypted_traffic_mirror = null
  # diffserv_forward - (optional) is a type of string
  diffserv_forward = null
  # diffserv_reverse - (optional) is a type of string
  diffserv_reverse = null
  # diffservcode_forward - (optional) is a type of string
  diffservcode_forward = null
  # diffservcode_rev - (optional) is a type of string
  diffservcode_rev = null
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
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = null
  # firewall_session_dirty - (optional) is a type of string
  firewall_session_dirty = null
  # fixedport - (optional) is a type of string
  fixedport = null
  # global_label - (optional) is a type of string
  global_label = null
  # http_policy_redirect - (optional) is a type of string
  http_policy_redirect = null
  # icap_profile - (optional) is a type of string
  icap_profile = null
  # inbound - (optional) is a type of string
  inbound = null
  # inspection_mode - (optional) is a type of string
  inspection_mode = null
  # ippool - (optional) is a type of string
  ippool = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # label - (optional) is a type of string
  label = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = null
  # name - (optional) is a type of string
  name = null
  # nat - (optional) is a type of string
  nat = null
  # natinbound - (optional) is a type of string
  natinbound = null
  # natoutbound - (optional) is a type of string
  natoutbound = null
  # outbound - (optional) is a type of string
  outbound = null
  # per_ip_shaper - (optional) is a type of string
  per_ip_shaper = null
  # policyid - (optional) is a type of number
  policyid = null
  # profile_group - (optional) is a type of string
  profile_group = null
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = null
  # profile_type - (optional) is a type of string
  profile_type = null
  # replacemsg_override_group - (optional) is a type of string
  replacemsg_override_group = null
  # rsso - (optional) is a type of string
  rsso = null
  # schedule - (required) is a type of string
  schedule = null
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

  dstintf = [{
    name = null
  }]

  fsso_groups = [{
    name = null
  }]

  groups = [{
    name = null
  }]

  poolname = [{
    name = null
  }]

  service = [{
    name = null
  }]

  srcaddr = [{
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

variable "emailfilter_profile" {
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

variable "natoutbound" {
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

variable "replacemsg_override_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(required)"
  type        = string
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
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
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

variable "poolname" {
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

variable "srcaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
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
resource "fortios_firewall_policy6" "this" {
  action                    = var.action
  anti_replay               = var.anti_replay
  application_list          = var.application_list
  auto_asic_offload         = var.auto_asic_offload
  av_profile                = var.av_profile
  cifs_profile              = var.cifs_profile
  comments                  = var.comments
  decrypted_traffic_mirror  = var.decrypted_traffic_mirror
  diffserv_forward          = var.diffserv_forward
  diffserv_reverse          = var.diffserv_reverse
  diffservcode_forward      = var.diffservcode_forward
  diffservcode_rev          = var.diffservcode_rev
  dlp_sensor                = var.dlp_sensor
  dnsfilter_profile         = var.dnsfilter_profile
  dsri                      = var.dsri
  dstaddr_negate            = var.dstaddr_negate
  dynamic_sort_subtable     = var.dynamic_sort_subtable
  emailfilter_profile       = var.emailfilter_profile
  firewall_session_dirty    = var.firewall_session_dirty
  fixedport                 = var.fixedport
  global_label              = var.global_label
  http_policy_redirect      = var.http_policy_redirect
  icap_profile              = var.icap_profile
  inbound                   = var.inbound
  inspection_mode           = var.inspection_mode
  ippool                    = var.ippool
  ips_sensor                = var.ips_sensor
  label                     = var.label
  logtraffic                = var.logtraffic
  logtraffic_start          = var.logtraffic_start
  name                      = var.name
  nat                       = var.nat
  natinbound                = var.natinbound
  natoutbound               = var.natoutbound
  outbound                  = var.outbound
  per_ip_shaper             = var.per_ip_shaper
  policyid                  = var.policyid
  profile_group             = var.profile_group
  profile_protocol_options  = var.profile_protocol_options
  profile_type              = var.profile_type
  replacemsg_override_group = var.replacemsg_override_group
  rsso                      = var.rsso
  schedule                  = var.schedule
  send_deny_packet          = var.send_deny_packet
  service_negate            = var.service_negate
  session_ttl               = var.session_ttl
  spamfilter_profile        = var.spamfilter_profile
  srcaddr_negate            = var.srcaddr_negate
  ssh_filter_profile        = var.ssh_filter_profile
  ssh_policy_redirect       = var.ssh_policy_redirect
  ssl_mirror                = var.ssl_mirror
  ssl_ssh_profile           = var.ssl_ssh_profile
  status                    = var.status
  tcp_mss_receiver          = var.tcp_mss_receiver
  tcp_mss_sender            = var.tcp_mss_sender
  tcp_session_without_syn   = var.tcp_session_without_syn
  timeout_send_rst          = var.timeout_send_rst
  tos                       = var.tos
  tos_mask                  = var.tos_mask
  tos_negate                = var.tos_negate
  traffic_shaper            = var.traffic_shaper
  traffic_shaper_reverse    = var.traffic_shaper_reverse
  utm_status                = var.utm_status
  uuid                      = var.uuid
  vlan_cos_fwd              = var.vlan_cos_fwd
  vlan_cos_rev              = var.vlan_cos_rev
  vlan_filter               = var.vlan_filter
  voip_profile              = var.voip_profile
  vpntunnel                 = var.vpntunnel
  waf_profile               = var.waf_profile
  webcache                  = var.webcache
  webcache_https            = var.webcache_https
  webfilter_profile         = var.webfilter_profile
  webproxy_forward_server   = var.webproxy_forward_server
  webproxy_profile          = var.webproxy_profile

  dynamic "app_category" {
    for_each = var.app_category
    content {
      id = app_category.value["id"]
    }
  }

  dynamic "app_group" {
    for_each = var.app_group
    content {
      name = app_group.value["name"]
    }
  }

  dynamic "application" {
    for_each = var.application
    content {
      id = application.value["id"]
    }
  }

  dynamic "custom_log_fields" {
    for_each = var.custom_log_fields
    content {
      field_id = custom_log_fields.value["field_id"]
    }
  }

  dynamic "devices" {
    for_each = var.devices
    content {
      name = devices.value["name"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
    }
  }

  dynamic "dstintf" {
    for_each = var.dstintf
    content {
      name = dstintf.value["name"]
    }
  }

  dynamic "fsso_groups" {
    for_each = var.fsso_groups
    content {
      name = fsso_groups.value["name"]
    }
  }

  dynamic "groups" {
    for_each = var.groups
    content {
      name = groups.value["name"]
    }
  }

  dynamic "poolname" {
    for_each = var.poolname
    content {
      name = poolname.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      name = service.value["name"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      name = srcaddr.value["name"]
    }
  }

  dynamic "srcintf" {
    for_each = var.srcintf
    content {
      name = srcintf.value["name"]
    }
  }

  dynamic "ssl_mirror_intf" {
    for_each = var.ssl_mirror_intf
    content {
      name = ssl_mirror_intf.value["name"]
    }
  }

  dynamic "url_category" {
    for_each = var.url_category
    content {
      id = url_category.value["id"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
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
  value       = fortios_firewall_policy6.this.action
}

output "anti_replay" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.anti_replay
}

output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.application_list
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.auto_asic_offload
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.av_profile
}

output "cifs_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.cifs_profile
}

output "decrypted_traffic_mirror" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.decrypted_traffic_mirror
}

output "diffserv_forward" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.diffservcode_rev
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.dnsfilter_profile
}

output "dsri" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.dsri
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.dstaddr_negate
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.emailfilter_profile
}

output "firewall_session_dirty" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.firewall_session_dirty
}

output "fixedport" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.fixedport
}

output "global_label" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.global_label
}

output "http_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.http_policy_redirect
}

output "icap_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.id
}

output "inbound" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.inbound
}

output "inspection_mode" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.inspection_mode
}

output "ippool" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.ips_sensor
}

output "label" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.label
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.name
}

output "nat" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.nat
}

output "natinbound" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.natinbound
}

output "natoutbound" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.natoutbound
}

output "outbound" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.outbound
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.per_ip_shaper
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_policy6.this.policyid
}

output "profile_group" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.profile_type
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.replacemsg_override_group
}

output "rsso" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.rsso
}

output "send_deny_packet" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.send_deny_packet
}

output "service_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = fortios_firewall_policy6.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.spamfilter_profile
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.srcaddr_negate
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.ssh_policy_redirect
}

output "ssl_mirror" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.ssl_mirror
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = fortios_firewall_policy6.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = fortios_firewall_policy6.this.tcp_mss_sender
}

output "tcp_session_without_syn" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.tcp_session_without_syn
}

output "timeout_send_rst" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.timeout_send_rst
}

output "tos" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.tos_mask
}

output "tos_negate" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.tos_negate
}

output "traffic_shaper" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.traffic_shaper_reverse
}

output "utm_status" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.uuid
}

output "vlan_cos_fwd" {
  description = "returns a number"
  value       = fortios_firewall_policy6.this.vlan_cos_fwd
}

output "vlan_cos_rev" {
  description = "returns a number"
  value       = fortios_firewall_policy6.this.vlan_cos_rev
}

output "vlan_filter" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.vlan_filter
}

output "voip_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.voip_profile
}

output "vpntunnel" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.vpntunnel
}

output "waf_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.waf_profile
}

output "webcache" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = fortios_firewall_policy6.this.webproxy_profile
}

output "this" {
  value = fortios_firewall_policy6.this
}
```

[top](#index)