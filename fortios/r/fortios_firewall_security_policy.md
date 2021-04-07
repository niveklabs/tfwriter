# fortios_firewall_security_policy

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
module "fortios_firewall_security_policy" {
  source = "./modules/fortios/r/fortios_firewall_security_policy"

  # action - (required) is a type of string
  action = null
  # application_list - (optional) is a type of string
  application_list = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # capture_packet - (optional) is a type of string
  capture_packet = null
  # comments - (optional) is a type of string
  comments = null
  # devices - (optional) is a type of list of string
  devices = []
  # dnsfilter_profile - (optional) is a type of string
  dnsfilter_profile = null
  # dstaddr - (required) is a type of list of string
  dstaddr = []
  # dstintf - (required) is a type of list of string
  dstintf = []
  # groups - (optional) is a type of list of string
  groups = []
  # internet_service - (optional) is a type of string
  internet_service = null
  # internet_service_id - (optional) is a type of list of number
  internet_service_id = []
  # internet_service_src - (optional) is a type of string
  internet_service_src = null
  # internet_service_src_id - (optional) is a type of list of number
  internet_service_src_id = []
  # ippool - (optional) is a type of string
  ippool = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = null
  # name - (required) is a type of string
  name = null
  # nat - (optional) is a type of string
  nat = null
  # poolname - (optional) is a type of list of string
  poolname = []
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = null
  # schedule - (required) is a type of string
  schedule = null
  # service - (required) is a type of list of string
  service = []
  # srcaddr - (required) is a type of list of string
  srcaddr = []
  # srcintf - (required) is a type of list of string
  srcintf = []
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = null
  # status - (optional) is a type of string
  status = null
  # users - (optional) is a type of list of string
  users = []
  # utm_status - (optional) is a type of string
  utm_status = null
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
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

variable "devices" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dnsfilter_profile" {
  description = "(optional)"
  type        = string
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

variable "groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "internet_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_id" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "internet_service_src" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_src_id" {
  description = "(optional)"
  type        = list(number)
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
  description = "(required)"
  type        = string
}

variable "nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "poolname" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "profile_protocol_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(required)"
  type        = string
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

variable "webfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_security_policy" "this" {
  # action - (required) is a type of string
  action = var.action
  # application_list - (optional) is a type of string
  application_list = var.application_list
  # av_profile - (optional) is a type of string
  av_profile = var.av_profile
  # capture_packet - (optional) is a type of string
  capture_packet = var.capture_packet
  # comments - (optional) is a type of string
  comments = var.comments
  # devices - (optional) is a type of list of string
  devices = var.devices
  # dnsfilter_profile - (optional) is a type of string
  dnsfilter_profile = var.dnsfilter_profile
  # dstaddr - (required) is a type of list of string
  dstaddr = var.dstaddr
  # dstintf - (required) is a type of list of string
  dstintf = var.dstintf
  # groups - (optional) is a type of list of string
  groups = var.groups
  # internet_service - (optional) is a type of string
  internet_service = var.internet_service
  # internet_service_id - (optional) is a type of list of number
  internet_service_id = var.internet_service_id
  # internet_service_src - (optional) is a type of string
  internet_service_src = var.internet_service_src
  # internet_service_src_id - (optional) is a type of list of number
  internet_service_src_id = var.internet_service_src_id
  # ippool - (optional) is a type of string
  ippool = var.ippool
  # ips_sensor - (optional) is a type of string
  ips_sensor = var.ips_sensor
  # logtraffic - (optional) is a type of string
  logtraffic = var.logtraffic
  # logtraffic_start - (optional) is a type of string
  logtraffic_start = var.logtraffic_start
  # name - (required) is a type of string
  name = var.name
  # nat - (optional) is a type of string
  nat = var.nat
  # poolname - (optional) is a type of list of string
  poolname = var.poolname
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = var.profile_protocol_options
  # schedule - (required) is a type of string
  schedule = var.schedule
  # service - (required) is a type of list of string
  service = var.service
  # srcaddr - (required) is a type of list of string
  srcaddr = var.srcaddr
  # srcintf - (required) is a type of list of string
  srcintf = var.srcintf
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = var.ssl_ssh_profile
  # status - (optional) is a type of string
  status = var.status
  # users - (optional) is a type of list of string
  users = var.users
  # utm_status - (optional) is a type of string
  utm_status = var.utm_status
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = var.webfilter_profile
}
```

[top](#index)

### Outputs

```terraform
output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.application_list
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.av_profile
}

output "capture_packet" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.capture_packet
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.dnsfilter_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.id
}

output "internet_service" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.internet_service
}

output "internet_service_src" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.internet_service_src
}

output "ippool" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.ippool
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.ips_sensor
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.logtraffic_start
}

output "nat" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.nat
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.profile_protocol_options
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.ssl_ssh_profile
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.status
}

output "utm_status" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.utm_status
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_security_policy.this.webfilter_profile
}

output "this" {
  value = fortios_firewall_security_policy.this
}
```

[top](#index)