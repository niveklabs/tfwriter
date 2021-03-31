# fortios_firewall_proxypolicy

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
module "fortios_firewall_proxypolicy" {
  source = "./modules/fortios/r/fortios_firewall_proxypolicy"

  # action - (optional) is a type of string
  action = null
  # application_list - (optional) is a type of string
  application_list = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # cifs_profile - (optional) is a type of string
  cifs_profile = null
  # comments - (optional) is a type of string
  comments = null
  # decrypted_traffic_mirror - (optional) is a type of string
  decrypted_traffic_mirror = null
  # disclaimer - (optional) is a type of string
  disclaimer = null
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = null
  # dstaddr_negate - (optional) is a type of string
  dstaddr_negate = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = null
  # file_filter_profile - (optional) is a type of string
  file_filter_profile = null
  # global_label - (optional) is a type of string
  global_label = null
  # http_tunnel_auth - (optional) is a type of string
  http_tunnel_auth = null
  # icap_profile - (optional) is a type of string
  icap_profile = null
  # internet_service - (optional) is a type of string
  internet_service = null
  # internet_service_negate - (optional) is a type of string
  internet_service_negate = null
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
  # policyid - (optional) is a type of number
  policyid = null
  # profile_group - (optional) is a type of string
  profile_group = null
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = null
  # profile_type - (optional) is a type of string
  profile_type = null
  # proxy - (required) is a type of string
  proxy = null
  # redirect_url - (optional) is a type of string
  redirect_url = null
  # replacemsg_override_group - (optional) is a type of string
  replacemsg_override_group = null
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = null
  # schedule - (required) is a type of string
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
  # transparent - (optional) is a type of string
  transparent = null
  # utm_status - (optional) is a type of string
  utm_status = null
  # uuid - (optional) is a type of string
  uuid = null
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

  dstaddr = [{
    name = null
  }]

  dstaddr6 = [{
    name = null
  }]

  dstintf = [{
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

  poolname = [{
    name = null
  }]

  service = [{
    name = null
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

variable "file_filter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_tunnel_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icap_profile" {
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

variable "proxy" {
  description = "(required)"
  type        = string
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

variable "scan_botnet_connections" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(required)"
  type        = string
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

variable "transparent" {
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
resource "fortios_firewall_proxypolicy" "this" {
  action                    = var.action
  application_list          = var.application_list
  av_profile                = var.av_profile
  cifs_profile              = var.cifs_profile
  comments                  = var.comments
  decrypted_traffic_mirror  = var.decrypted_traffic_mirror
  disclaimer                = var.disclaimer
  dlp_sensor                = var.dlp_sensor
  dstaddr_negate            = var.dstaddr_negate
  dynamic_sort_subtable     = var.dynamic_sort_subtable
  emailfilter_profile       = var.emailfilter_profile
  file_filter_profile       = var.file_filter_profile
  global_label              = var.global_label
  http_tunnel_auth          = var.http_tunnel_auth
  icap_profile              = var.icap_profile
  internet_service          = var.internet_service
  internet_service_negate   = var.internet_service_negate
  ips_sensor                = var.ips_sensor
  label                     = var.label
  logtraffic                = var.logtraffic
  logtraffic_start          = var.logtraffic_start
  name                      = var.name
  policyid                  = var.policyid
  profile_group             = var.profile_group
  profile_protocol_options  = var.profile_protocol_options
  profile_type              = var.profile_type
  proxy                     = var.proxy
  redirect_url              = var.redirect_url
  replacemsg_override_group = var.replacemsg_override_group
  scan_botnet_connections   = var.scan_botnet_connections
  schedule                  = var.schedule
  service_negate            = var.service_negate
  session_ttl               = var.session_ttl
  spamfilter_profile        = var.spamfilter_profile
  srcaddr_negate            = var.srcaddr_negate
  ssh_filter_profile        = var.ssh_filter_profile
  ssh_policy_redirect       = var.ssh_policy_redirect
  ssl_ssh_profile           = var.ssl_ssh_profile
  status                    = var.status
  transparent               = var.transparent
  utm_status                = var.utm_status
  uuid                      = var.uuid
  waf_profile               = var.waf_profile
  webcache                  = var.webcache
  webcache_https            = var.webcache_https
  webfilter_profile         = var.webfilter_profile
  webproxy_forward_server   = var.webproxy_forward_server
  webproxy_profile          = var.webproxy_profile

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
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
  value       = fortios_firewall_proxypolicy.this.action
}

output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.application_list
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.av_profile
}

output "cifs_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.cifs_profile
}

output "decrypted_traffic_mirror" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.decrypted_traffic_mirror
}

output "disclaimer" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.disclaimer
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.dlp_sensor
}

output "dstaddr_negate" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.dstaddr_negate
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.emailfilter_profile
}

output "file_filter_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.file_filter_profile
}

output "global_label" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.global_label
}

output "http_tunnel_auth" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.http_tunnel_auth
}

output "icap_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.id
}

output "internet_service" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.internet_service
}

output "internet_service_negate" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.internet_service_negate
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.ips_sensor
}

output "label" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.label
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.name
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_proxypolicy.this.policyid
}

output "profile_group" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.profile_group
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.profile_protocol_options
}

output "profile_type" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.profile_type
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.replacemsg_override_group
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.scan_botnet_connections
}

output "service_negate" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.service_negate
}

output "session_ttl" {
  description = "returns a number"
  value       = fortios_firewall_proxypolicy.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.spamfilter_profile
}

output "srcaddr_negate" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.srcaddr_negate
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.ssh_filter_profile
}

output "ssh_policy_redirect" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.ssh_policy_redirect
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.status
}

output "transparent" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.transparent
}

output "utm_status" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.utm_status
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.uuid
}

output "waf_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.waf_profile
}

output "webcache" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.webcache
}

output "webcache_https" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.webcache_https
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.webfilter_profile
}

output "webproxy_forward_server" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.webproxy_forward_server
}

output "webproxy_profile" {
  description = "returns a string"
  value       = fortios_firewall_proxypolicy.this.webproxy_profile
}

output "this" {
  value = fortios_firewall_proxypolicy.this
}
```

[top](#index)