# fortios_firewallconsolidated_policy

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
module "fortios_firewallconsolidated_policy" {
  source = "./modules/fortios/r/fortios_firewallconsolidated_policy"

  # action - (optional) is a type of string
  action = null
  # application_list - (optional) is a type of string
  application_list = null
  # auto_asic_offload - (optional) is a type of string
  auto_asic_offload = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # captive_portal_exempt - (optional) is a type of string
  captive_portal_exempt = null
  # cifs_profile - (optional) is a type of string
  cifs_profile = null
  # comments - (optional) is a type of string
  comments = null
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
  # dstaddr_negate - (optional) is a type of string
  dstaddr_negate = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = null
  # fixedport - (optional) is a type of string
  fixedport = null
  # http_policy_redirect - (optional) is a type of string
  http_policy_redirect = null
  # icap_profile - (optional) is a type of string
  icap_profile = null
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
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = null
  # name - (optional) is a type of string
  name = null
  # nat - (optional) is a type of string
  nat = null
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
  # schedule - (optional) is a type of string
  schedule = null
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
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = null
  # status - (optional) is a type of string
  status = null
  # tcp_mss_receiver - (optional) is a type of number
  tcp_mss_receiver = null
  # tcp_mss_sender - (optional) is a type of number
  tcp_mss_sender = null
  # traffic_shaper - (optional) is a type of string
  traffic_shaper = null
  # traffic_shaper_reverse - (optional) is a type of string
  traffic_shaper_reverse = null
  # utm_status - (optional) is a type of string
  utm_status = null
  # uuid - (optional) is a type of string
  uuid = null
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

  dstaddr4 = [{
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

  poolname4 = [{
    name = null
  }]

  poolname6 = [{
    name = null
  }]

  service = [{
    name = null
  }]

  srcaddr4 = [{
    name = null
  }]

  srcaddr6 = [{
    name = null
  }]

  srcintf = [{
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

variable "captive_portal_exempt" {
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

variable "fixedport" {
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

variable "schedule" {
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

variable "dstaddr4" {
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
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
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

variable "poolname4" {
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

variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcaddr4" {
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
resource "fortios_firewallconsolidated_policy" "this" {
  action                      = var.action
  application_list            = var.application_list
  auto_asic_offload           = var.auto_asic_offload
  av_profile                  = var.av_profile
  captive_portal_exempt       = var.captive_portal_exempt
  cifs_profile                = var.cifs_profile
  comments                    = var.comments
  diffserv_forward            = var.diffserv_forward
  diffserv_reverse            = var.diffserv_reverse
  diffservcode_forward        = var.diffservcode_forward
  diffservcode_rev            = var.diffservcode_rev
  dlp_sensor                  = var.dlp_sensor
  dnsfilter_profile           = var.dnsfilter_profile
  dstaddr_negate              = var.dstaddr_negate
  dynamic_sort_subtable       = var.dynamic_sort_subtable
  emailfilter_profile         = var.emailfilter_profile
  fixedport                   = var.fixedport
  http_policy_redirect        = var.http_policy_redirect
  icap_profile                = var.icap_profile
  inbound                     = var.inbound
  inspection_mode             = var.inspection_mode
  internet_service            = var.internet_service
  internet_service_negate     = var.internet_service_negate
  internet_service_src        = var.internet_service_src
  internet_service_src_negate = var.internet_service_src_negate
  ippool                      = var.ippool
  ips_sensor                  = var.ips_sensor
  logtraffic                  = var.logtraffic
  logtraffic_start            = var.logtraffic_start
  name                        = var.name
  nat                         = var.nat
  outbound                    = var.outbound
  per_ip_shaper               = var.per_ip_shaper
  policyid                    = var.policyid
  profile_group               = var.profile_group
  profile_protocol_options    = var.profile_protocol_options
  profile_type                = var.profile_type
  schedule                    = var.schedule
  service_negate              = var.service_negate
  session_ttl                 = var.session_ttl
  spamfilter_profile          = var.spamfilter_profile
  srcaddr_negate              = var.srcaddr_negate
  ssh_filter_profile          = var.ssh_filter_profile
  ssh_policy_redirect         = var.ssh_policy_redirect
  ssl_ssh_profile             = var.ssl_ssh_profile
  status                      = var.status
  tcp_mss_receiver            = var.tcp_mss_receiver
  tcp_mss_sender              = var.tcp_mss_sender
  traffic_shaper              = var.traffic_shaper
  traffic_shaper_reverse      = var.traffic_shaper_reverse
  utm_status                  = var.utm_status
  uuid                        = var.uuid
  voip_profile                = var.voip_profile
  vpntunnel                   = var.vpntunnel
  waf_profile                 = var.waf_profile
  wanopt                      = var.wanopt
  wanopt_detection            = var.wanopt_detection
  wanopt_passive_opt          = var.wanopt_passive_opt
  wanopt_peer                 = var.wanopt_peer
  wanopt_profile              = var.wanopt_profile
  webcache                    = var.webcache
  webcache_https              = var.webcache_https
  webfilter_profile           = var.webfilter_profile
  webproxy_forward_server     = var.webproxy_forward_server
  webproxy_profile            = var.webproxy_profile

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

  dynamic "dstaddr4" {
    for_each = var.dstaddr4
    content {
      name = dstaddr4.value["name"]
    }
  }

  dynamic "dstaddr6" {
    for_each = var.dstaddr6
    content {
      name = dstaddr6.value["name"]
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

  dynamic "internet_service_custom" {
    for_each = var.internet_service_custom
    content {
      name = internet_service_custom.value["name"]
    }
  }

  dynamic "internet_service_custom_group" {
    for_each = var.internet_service_custom_group
    content {
      name = internet_service_custom_group.value["name"]
    }
  }

  dynamic "internet_service_group" {
    for_each = var.internet_service_group
    content {
      name = internet_service_group.value["name"]
    }
  }

  dynamic "internet_service_id" {
    for_each = var.internet_service_id
    content {
      id = internet_service_id.value["id"]
    }
  }

  dynamic "internet_service_name" {
    for_each = var.internet_service_name
    content {
      name = internet_service_name.value["name"]
    }
  }

  dynamic "internet_service_src_custom" {
    for_each = var.internet_service_src_custom
    content {
      name = internet_service_src_custom.value["name"]
    }
  }

  dynamic "internet_service_src_custom_group" {
    for_each = var.internet_service_src_custom_group
    content {
      name = internet_service_src_custom_group.value["name"]
    }
  }

  dynamic "internet_service_src_group" {
    for_each = var.internet_service_src_group
    content {
      name = internet_service_src_group.value["name"]
    }
  }

  dynamic "internet_service_src_id" {
    for_each = var.internet_service_src_id
    content {
      id = internet_service_src_id.value["id"]
    }
  }

  dynamic "internet_service_src_name" {
    for_each = var.internet_service_src_name
    content {
      name = internet_service_src_name.value["name"]
    }
  }

  dynamic "poolname4" {
    for_each = var.poolname4
    content {
      name = poolname4.value["name"]
    }
  }

  dynamic "poolname6" {
    for_each = var.poolname6
    content {
      name = poolname6.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      name = service.value["name"]
    }
  }

  dynamic "srcaddr4" {
    for_each = var.srcaddr4
    content {
      name = srcaddr4.value["name"]
    }
  }

  dynamic "srcaddr6" {
    for_each = var.srcaddr6
    content {
      name = srcaddr6.value["name"]
    }
  }

  dynamic "srcintf" {
    for_each = var.srcintf
    content {
      name = srcintf.value["name"]
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
  value       = fortios_firewallconsolidated_policy.this.action
}

output "application_list" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.application_list
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.auto_asic_offload
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.av_profile
}

output "captive_portal_exempt" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.captive_portal_exempt
}

output "cifs_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.cifs_profile
}

output "diffserv_forward" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.diffservcode_rev
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.dnsfilter_profile
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.dstaddr_negate
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.emailfilter_profile
}

output "fixedport" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.fixedport
}

output "http_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.http_policy_redirect
}

output "icap_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.id
}

output "inbound" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.inbound
}

output "inspection_mode" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.inspection_mode
}

output "internet_service" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.internet_service
}

output "internet_service_negate" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.internet_service_negate
}

output "internet_service_src" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.internet_service_src
}

output "internet_service_src_negate" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.internet_service_src_negate
}

output "ippool" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.ips_sensor
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.name
}

output "nat" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.nat
}

output "outbound" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.outbound
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.per_ip_shaper
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewallconsolidated_policy.this.policyid
}

output "profile_group" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.profile_type
}

output "schedule" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.schedule
}

output "service_negate" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = fortios_firewallconsolidated_policy.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.spamfilter_profile
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.srcaddr_negate
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.ssh_policy_redirect
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = fortios_firewallconsolidated_policy.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = fortios_firewallconsolidated_policy.this.tcp_mss_sender
}

output "traffic_shaper" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.traffic_shaper_reverse
}

output "utm_status" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.uuid
}

output "voip_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.voip_profile
}

output "vpntunnel" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.vpntunnel
}

output "waf_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.waf_profile
}

output "wanopt" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.wanopt
}

output "wanopt_detection" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.wanopt_detection
}

output "wanopt_passive_opt" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.wanopt_passive_opt
}

output "wanopt_peer" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.wanopt_peer
}

output "wanopt_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.wanopt_profile
}

output "webcache" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.webproxy_profile
}

output "this" {
  value = fortios_firewallconsolidated_policy.this
}
```

[top](#index)