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
    fortios = ">= 1.6.18"
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
  # av_profile - (optional) is a type of string
  av_profile = null
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
  # fixedport - (optional) is a type of string
  fixedport = null
  # icap_profile - (optional) is a type of string
  icap_profile = null
  # inbound - (optional) is a type of string
  inbound = null
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
  # session_ttl - (optional) is a type of number
  session_ttl = null
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = null
  # ssh_filter_profile - (optional) is a type of string
  ssh_filter_profile = null
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
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null

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

  groups = [{
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

variable "av_profile" {
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

variable "fixedport" {
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

variable "ssh_filter_profile" {
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

variable "webfilter_profile" {
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

variable "groups" {
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
  action                   = var.action
  application_list         = var.application_list
  av_profile               = var.av_profile
  comments                 = var.comments
  diffserv_forward         = var.diffserv_forward
  diffserv_reverse         = var.diffserv_reverse
  diffservcode_forward     = var.diffservcode_forward
  diffservcode_rev         = var.diffservcode_rev
  dlp_sensor               = var.dlp_sensor
  dnsfilter_profile        = var.dnsfilter_profile
  fixedport                = var.fixedport
  icap_profile             = var.icap_profile
  inbound                  = var.inbound
  ippool                   = var.ippool
  ips_sensor               = var.ips_sensor
  logtraffic               = var.logtraffic
  logtraffic_start         = var.logtraffic_start
  name                     = var.name
  nat                      = var.nat
  outbound                 = var.outbound
  per_ip_shaper            = var.per_ip_shaper
  policyid                 = var.policyid
  profile_group            = var.profile_group
  profile_protocol_options = var.profile_protocol_options
  profile_type             = var.profile_type
  schedule                 = var.schedule
  session_ttl              = var.session_ttl
  spamfilter_profile       = var.spamfilter_profile
  ssh_filter_profile       = var.ssh_filter_profile
  ssl_ssh_profile          = var.ssl_ssh_profile
  status                   = var.status
  tcp_mss_receiver         = var.tcp_mss_receiver
  tcp_mss_sender           = var.tcp_mss_sender
  traffic_shaper           = var.traffic_shaper
  traffic_shaper_reverse   = var.traffic_shaper_reverse
  utm_status               = var.utm_status
  uuid                     = var.uuid
  voip_profile             = var.voip_profile
  vpntunnel                = var.vpntunnel
  waf_profile              = var.waf_profile
  webfilter_profile        = var.webfilter_profile

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

  dynamic "groups" {
    for_each = var.groups
    content {
      name = groups.value["name"]
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

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.av_profile
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

output "fixedport" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.fixedport
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

output "session_ttl" {
  description = "returns a number"
  value       = fortios_firewallconsolidated_policy.this.session_ttl
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.spamfilter_profile
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.ssh_filter_profile
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

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewallconsolidated_policy.this.webfilter_profile
}

output "this" {
  value = fortios_firewallconsolidated_policy.this
}
```

[top](#index)