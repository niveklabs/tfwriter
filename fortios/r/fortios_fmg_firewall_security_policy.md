# fortios_fmg_firewall_security_policy

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
module "fortios_fmg_firewall_security_policy" {
  source = "./modules/fortios/r/fortios_fmg_firewall_security_policy"

  # action - (optional) is a type of string
  action = null
  # adom - (optional) is a type of string
  adom = null
  # application_list - (optional) is a type of list of string
  application_list = []
  # av_profile - (optional) is a type of list of string
  av_profile = []
  # capture_packet - (optional) is a type of string
  capture_packet = null
  # comments - (optional) is a type of string
  comments = null
  # dnsfilter_profile - (optional) is a type of list of string
  dnsfilter_profile = []
  # dstaddr - (required) is a type of list of string
  dstaddr = []
  # dstintf - (required) is a type of list of string
  dstintf = []
  # fixedport - (optional) is a type of string
  fixedport = null
  # fsso - (optional) is a type of string
  fsso = null
  # groups - (optional) is a type of list of string
  groups = []
  # inbound - (optional) is a type of string
  inbound = null
  # internet_service - (optional) is a type of string
  internet_service = null
  # internet_service_id - (optional) is a type of list of string
  internet_service_id = []
  # internet_service_name - (optional) is a type of list of string
  internet_service_name = []
  # internet_service_src - (optional) is a type of string
  internet_service_src = null
  # internet_service_src_id - (optional) is a type of list of string
  internet_service_src_id = []
  # internet_service_src_name - (optional) is a type of list of string
  internet_service_src_name = []
  # ippool - (optional) is a type of string
  ippool = null
  # ips_sensor - (optional) is a type of list of string
  ips_sensor = []
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = null
  # name - (required) is a type of string
  name = null
  # nat - (optional) is a type of string
  nat = null
  # package_name - (optional) is a type of string
  package_name = null
  # per_ip_shaper - (optional) is a type of list of string
  per_ip_shaper = []
  # poolname - (optional) is a type of list of string
  poolname = []
  # profile_group - (optional) is a type of list of string
  profile_group = []
  # profile_protocol_options - (optional) is a type of list of string
  profile_protocol_options = []
  # profile_type - (optional) is a type of string
  profile_type = null
  # rsso - (optional) is a type of string
  rsso = null
  # schedule - (required) is a type of list of string
  schedule = []
  # service - (required) is a type of list of string
  service = []
  # srcaddr - (required) is a type of list of string
  srcaddr = []
  # srcintf - (required) is a type of list of string
  srcintf = []
  # traffic_shaper - (optional) is a type of list of string
  traffic_shaper = []
  # traffic_shaper_reverse - (optional) is a type of list of string
  traffic_shaper_reverse = []
  # users - (optional) is a type of list of string
  users = []
  # utm_status - (optional) is a type of string
  utm_status = null
  # vpn_tunnel - (optional) is a type of list of string
  vpn_tunnel = []
  # waf_profile - (optional) is a type of list of string
  waf_profile = []
  # webfilter_profile - (optional) is a type of list of string
  webfilter_profile = []
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

variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "av_profile" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "capture_packet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnsfilter_profile" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dstaddr" {
  description = "(required)"
  type        = list(string)
}

variable "dstintf" {
  description = "(required)"
  type        = list(string)
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

variable "groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "inbound" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_id" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "internet_service_name" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "internet_service_src" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_src_id" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "internet_service_src_name" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ippool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_sensor" {
  description = "(optional)"
  type        = list(string)
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
  description = "(required)"
  type        = string
}

variable "nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_ip_shaper" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "poolname" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "profile_group" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "profile_protocol_options" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "profile_type" {
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
  type        = list(string)
}

variable "service" {
  description = "(required)"
  type        = list(string)
}

variable "srcaddr" {
  description = "(required)"
  type        = list(string)
}

variable "srcintf" {
  description = "(required)"
  type        = list(string)
}

variable "traffic_shaper" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "traffic_shaper_reverse" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "users" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "utm_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_tunnel" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "waf_profile" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "webfilter_profile" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_firewall_security_policy" "this" {
  action                    = var.action
  adom                      = var.adom
  application_list          = var.application_list
  av_profile                = var.av_profile
  capture_packet            = var.capture_packet
  comments                  = var.comments
  dnsfilter_profile         = var.dnsfilter_profile
  dstaddr                   = var.dstaddr
  dstintf                   = var.dstintf
  fixedport                 = var.fixedport
  fsso                      = var.fsso
  groups                    = var.groups
  inbound                   = var.inbound
  internet_service          = var.internet_service
  internet_service_id       = var.internet_service_id
  internet_service_name     = var.internet_service_name
  internet_service_src      = var.internet_service_src
  internet_service_src_id   = var.internet_service_src_id
  internet_service_src_name = var.internet_service_src_name
  ippool                    = var.ippool
  ips_sensor                = var.ips_sensor
  logtraffic                = var.logtraffic
  logtraffic_start          = var.logtraffic_start
  name                      = var.name
  nat                       = var.nat
  package_name              = var.package_name
  per_ip_shaper             = var.per_ip_shaper
  poolname                  = var.poolname
  profile_group             = var.profile_group
  profile_protocol_options  = var.profile_protocol_options
  profile_type              = var.profile_type
  rsso                      = var.rsso
  schedule                  = var.schedule
  service                   = var.service
  srcaddr                   = var.srcaddr
  srcintf                   = var.srcintf
  traffic_shaper            = var.traffic_shaper
  traffic_shaper_reverse    = var.traffic_shaper_reverse
  users                     = var.users
  utm_status                = var.utm_status
  vpn_tunnel                = var.vpn_tunnel
  waf_profile               = var.waf_profile
  webfilter_profile         = var.webfilter_profile
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_firewall_security_policy.this.id
}

output "internet_service" {
  description = "returns a string"
  value       = fortios_fmg_firewall_security_policy.this.internet_service
}

output "internet_service_src" {
  description = "returns a string"
  value       = fortios_fmg_firewall_security_policy.this.internet_service_src
}

output "this" {
  value = fortios_fmg_firewall_security_policy.this
}
```

[top](#index)