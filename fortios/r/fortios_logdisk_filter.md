# fortios_logdisk_filter

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
module "fortios_logdisk_filter" {
  source = "./modules/fortios/r/fortios_logdisk_filter"

  # admin - (optional) is a type of string
  admin = null
  # anomaly - (optional) is a type of string
  anomaly = null
  # auth - (optional) is a type of string
  auth = null
  # cpu_memory_usage - (optional) is a type of string
  cpu_memory_usage = null
  # dhcp - (optional) is a type of string
  dhcp = null
  # dlp_archive - (optional) is a type of string
  dlp_archive = null
  # dns - (optional) is a type of string
  dns = null
  # event - (optional) is a type of string
  event = null
  # filter - (optional) is a type of string
  filter = null
  # filter_type - (optional) is a type of string
  filter_type = null
  # forward_traffic - (optional) is a type of string
  forward_traffic = null
  # gtp - (optional) is a type of string
  gtp = null
  # ha - (optional) is a type of string
  ha = null
  # ipsec - (optional) is a type of string
  ipsec = null
  # ldb_monitor - (optional) is a type of string
  ldb_monitor = null
  # local_traffic - (optional) is a type of string
  local_traffic = null
  # multicast_traffic - (optional) is a type of string
  multicast_traffic = null
  # netscan_discovery - (optional) is a type of string
  netscan_discovery = null
  # netscan_vulnerability - (optional) is a type of string
  netscan_vulnerability = null
  # pattern - (optional) is a type of string
  pattern = null
  # ppp - (optional) is a type of string
  ppp = null
  # radius - (optional) is a type of string
  radius = null
  # severity - (optional) is a type of string
  severity = null
  # sniffer_traffic - (optional) is a type of string
  sniffer_traffic = null
  # ssh - (optional) is a type of string
  ssh = null
  # sslvpn_log_adm - (optional) is a type of string
  sslvpn_log_adm = null
  # sslvpn_log_auth - (optional) is a type of string
  sslvpn_log_auth = null
  # sslvpn_log_session - (optional) is a type of string
  sslvpn_log_session = null
  # system - (optional) is a type of string
  system = null
  # vip_ssl - (optional) is a type of string
  vip_ssl = null
  # voip - (optional) is a type of string
  voip = null
  # wan_opt - (optional) is a type of string
  wan_opt = null
  # wireless_activity - (optional) is a type of string
  wireless_activity = null
}
```

[top](#index)

### Variables

```terraform
variable "admin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anomaly" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_memory_usage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dlp_archive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gtp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldb_monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netscan_discovery" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netscan_vulnerability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sniffer_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_log_adm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_log_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_log_session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vip_ssl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wan_opt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wireless_activity" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logdisk_filter" "this" {
  admin                 = var.admin
  anomaly               = var.anomaly
  auth                  = var.auth
  cpu_memory_usage      = var.cpu_memory_usage
  dhcp                  = var.dhcp
  dlp_archive           = var.dlp_archive
  dns                   = var.dns
  event                 = var.event
  filter                = var.filter
  filter_type           = var.filter_type
  forward_traffic       = var.forward_traffic
  gtp                   = var.gtp
  ha                    = var.ha
  ipsec                 = var.ipsec
  ldb_monitor           = var.ldb_monitor
  local_traffic         = var.local_traffic
  multicast_traffic     = var.multicast_traffic
  netscan_discovery     = var.netscan_discovery
  netscan_vulnerability = var.netscan_vulnerability
  pattern               = var.pattern
  ppp                   = var.ppp
  radius                = var.radius
  severity              = var.severity
  sniffer_traffic       = var.sniffer_traffic
  ssh                   = var.ssh
  sslvpn_log_adm        = var.sslvpn_log_adm
  sslvpn_log_auth       = var.sslvpn_log_auth
  sslvpn_log_session    = var.sslvpn_log_session
  system                = var.system
  vip_ssl               = var.vip_ssl
  voip                  = var.voip
  wan_opt               = var.wan_opt
  wireless_activity     = var.wireless_activity
}
```

[top](#index)

### Outputs

```terraform
output "admin" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.admin
}

output "anomaly" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.anomaly
}

output "auth" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.auth
}

output "cpu_memory_usage" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.cpu_memory_usage
}

output "dhcp" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.dhcp
}

output "dlp_archive" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.dlp_archive
}

output "dns" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.dns
}

output "event" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.event
}

output "filter" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.filter
}

output "filter_type" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.filter_type
}

output "forward_traffic" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.forward_traffic
}

output "gtp" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.gtp
}

output "ha" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.ha
}

output "id" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.id
}

output "ipsec" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.ipsec
}

output "ldb_monitor" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.ldb_monitor
}

output "local_traffic" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.local_traffic
}

output "multicast_traffic" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.multicast_traffic
}

output "netscan_discovery" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.netscan_discovery
}

output "netscan_vulnerability" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.netscan_vulnerability
}

output "pattern" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.pattern
}

output "ppp" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.ppp
}

output "radius" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.radius
}

output "severity" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.severity
}

output "sniffer_traffic" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.sniffer_traffic
}

output "ssh" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.ssh
}

output "sslvpn_log_adm" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.sslvpn_log_adm
}

output "sslvpn_log_auth" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.sslvpn_log_auth
}

output "sslvpn_log_session" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.sslvpn_log_session
}

output "system" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.system
}

output "vip_ssl" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.vip_ssl
}

output "voip" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.voip
}

output "wan_opt" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.wan_opt
}

output "wireless_activity" {
  description = "returns a string"
  value       = fortios_logdisk_filter.this.wireless_activity
}

output "this" {
  value = fortios_logdisk_filter.this
}
```

[top](#index)