# fortios_firewall_sniffer

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
module "fortios_firewall_sniffer" {
  source = "./modules/fortios/r/fortios_firewall_sniffer"

  # application_list - (optional) is a type of string
  application_list = null
  # application_list_status - (optional) is a type of string
  application_list_status = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # av_profile_status - (optional) is a type of string
  av_profile_status = null
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = null
  # dlp_sensor_status - (optional) is a type of string
  dlp_sensor_status = null
  # dsri - (optional) is a type of string
  dsri = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = null
  # emailfilter_profile_status - (optional) is a type of string
  emailfilter_profile_status = null
  # fosid - (optional) is a type of number
  fosid = null
  # host - (optional) is a type of string
  host = null
  # interface - (required) is a type of string
  interface = null
  # ip_threatfeed_status - (optional) is a type of string
  ip_threatfeed_status = null
  # ips_dos_status - (optional) is a type of string
  ips_dos_status = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # ips_sensor_status - (optional) is a type of string
  ips_sensor_status = null
  # ipv6 - (optional) is a type of string
  ipv6 = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # max_packet_count - (optional) is a type of number
  max_packet_count = null
  # non_ip - (optional) is a type of string
  non_ip = null
  # port - (optional) is a type of string
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = null
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = null
  # spamfilter_profile_status - (optional) is a type of string
  spamfilter_profile_status = null
  # status - (optional) is a type of string
  status = null
  # vlan - (optional) is a type of string
  vlan = null
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null
  # webfilter_profile_status - (optional) is a type of string
  webfilter_profile_status = null

  anomaly = [{
    action            = null
    log               = null
    name              = null
    quarantine        = null
    quarantine_expiry = null
    quarantine_log    = null
    status            = null
    threshold         = null
    thresholddefault  = null
  }]

  ip_threatfeed = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_list_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "av_profile_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dlp_sensor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dlp_sensor_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dsri" {
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

variable "emailfilter_profile_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "ip_threatfeed_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_dos_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_sensor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_sensor_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logtraffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_packet_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "non_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_botnet_connections" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spamfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spamfilter_profile_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_profile_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anomaly" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action            = string
      log               = string
      name              = string
      quarantine        = string
      quarantine_expiry = string
      quarantine_log    = string
      status            = string
      threshold         = number
      thresholddefault  = number
    }
  ))
  default = []
}

variable "ip_threatfeed" {
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
resource "fortios_firewall_sniffer" "this" {
  # application_list - (optional) is a type of string
  application_list = var.application_list
  # application_list_status - (optional) is a type of string
  application_list_status = var.application_list_status
  # av_profile - (optional) is a type of string
  av_profile = var.av_profile
  # av_profile_status - (optional) is a type of string
  av_profile_status = var.av_profile_status
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = var.dlp_sensor
  # dlp_sensor_status - (optional) is a type of string
  dlp_sensor_status = var.dlp_sensor_status
  # dsri - (optional) is a type of string
  dsri = var.dsri
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # emailfilter_profile - (optional) is a type of string
  emailfilter_profile = var.emailfilter_profile
  # emailfilter_profile_status - (optional) is a type of string
  emailfilter_profile_status = var.emailfilter_profile_status
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # host - (optional) is a type of string
  host = var.host
  # interface - (required) is a type of string
  interface = var.interface
  # ip_threatfeed_status - (optional) is a type of string
  ip_threatfeed_status = var.ip_threatfeed_status
  # ips_dos_status - (optional) is a type of string
  ips_dos_status = var.ips_dos_status
  # ips_sensor - (optional) is a type of string
  ips_sensor = var.ips_sensor
  # ips_sensor_status - (optional) is a type of string
  ips_sensor_status = var.ips_sensor_status
  # ipv6 - (optional) is a type of string
  ipv6 = var.ipv6
  # logtraffic - (optional) is a type of string
  logtraffic = var.logtraffic
  # max_packet_count - (optional) is a type of number
  max_packet_count = var.max_packet_count
  # non_ip - (optional) is a type of string
  non_ip = var.non_ip
  # port - (optional) is a type of string
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = var.scan_botnet_connections
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = var.spamfilter_profile
  # spamfilter_profile_status - (optional) is a type of string
  spamfilter_profile_status = var.spamfilter_profile_status
  # status - (optional) is a type of string
  status = var.status
  # vlan - (optional) is a type of string
  vlan = var.vlan
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = var.webfilter_profile
  # webfilter_profile_status - (optional) is a type of string
  webfilter_profile_status = var.webfilter_profile_status

  dynamic "anomaly" {
    for_each = var.anomaly
    content {
      # action - (optional) is a type of string
      action = anomaly.value["action"]
      # log - (optional) is a type of string
      log = anomaly.value["log"]
      # name - (optional) is a type of string
      name = anomaly.value["name"]
      # quarantine - (optional) is a type of string
      quarantine = anomaly.value["quarantine"]
      # quarantine_expiry - (optional) is a type of string
      quarantine_expiry = anomaly.value["quarantine_expiry"]
      # quarantine_log - (optional) is a type of string
      quarantine_log = anomaly.value["quarantine_log"]
      # status - (optional) is a type of string
      status = anomaly.value["status"]
      # threshold - (optional) is a type of number
      threshold = anomaly.value["threshold"]
      # thresholddefault - (optional) is a type of number
      thresholddefault = anomaly.value["thresholddefault"]
    }
  }

  dynamic "ip_threatfeed" {
    for_each = var.ip_threatfeed
    content {
      # name - (optional) is a type of string
      name = ip_threatfeed.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.application_list
}

output "application_list_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.application_list_status
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.av_profile
}

output "av_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.av_profile_status
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.dlp_sensor
}

output "dlp_sensor_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.dlp_sensor_status
}

output "dsri" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.dsri
}

output "emailfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.emailfilter_profile
}

output "emailfilter_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.emailfilter_profile_status
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_sniffer.this.fosid
}

output "host" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.host
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.id
}

output "ip_threatfeed_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.ip_threatfeed_status
}

output "ips_dos_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.ips_dos_status
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.ips_sensor
}

output "ips_sensor_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.ips_sensor_status
}

output "ipv6" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.ipv6
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.logtraffic
}

output "max_packet_count" {
  description = "returns a number"
  value       = fortios_firewall_sniffer.this.max_packet_count
}

output "non_ip" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.non_ip
}

output "port" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.port
}

output "protocol" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.protocol
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.scan_botnet_connections
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.spamfilter_profile
}

output "spamfilter_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.spamfilter_profile_status
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.status
}

output "vlan" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.vlan
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.webfilter_profile
}

output "webfilter_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_sniffer.this.webfilter_profile_status
}

output "this" {
  value = fortios_firewall_sniffer.this
}
```

[top](#index)