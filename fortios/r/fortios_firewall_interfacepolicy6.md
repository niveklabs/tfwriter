# fortios_firewall_interfacepolicy6

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
module "fortios_firewall_interfacepolicy6" {
  source = "./modules/fortios/r/fortios_firewall_interfacepolicy6"

  # address_type - (optional) is a type of string
  address_type = null
  # application_list - (optional) is a type of string
  application_list = null
  # application_list_status - (optional) is a type of string
  application_list_status = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # av_profile_status - (optional) is a type of string
  av_profile_status = null
  # comments - (optional) is a type of string
  comments = null
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = null
  # dlp_sensor_status - (optional) is a type of string
  dlp_sensor_status = null
  # dsri - (optional) is a type of string
  dsri = null
  # interface - (required) is a type of string
  interface = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # ips_sensor_status - (optional) is a type of string
  ips_sensor_status = null
  # label - (optional) is a type of string
  label = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # policyid - (optional) is a type of number
  policyid = null
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = null
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = null
  # spamfilter_profile_status - (optional) is a type of string
  spamfilter_profile_status = null
  # status - (optional) is a type of string
  status = null
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null
  # webfilter_profile_status - (optional) is a type of string
  webfilter_profile_status = null

  dstaddr6 = [{
    name = null
  }]

  service6 = [{
    name = null
  }]

  srcaddr6 = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "comments" {
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

variable "interface" {
  description = "(required)"
  type        = string
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

variable "policyid" {
  description = "(optional)"
  type        = number
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

variable "dstaddr6" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "service6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcaddr6" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_interfacepolicy6" "this" {
  address_type              = var.address_type
  application_list          = var.application_list
  application_list_status   = var.application_list_status
  av_profile                = var.av_profile
  av_profile_status         = var.av_profile_status
  comments                  = var.comments
  dlp_sensor                = var.dlp_sensor
  dlp_sensor_status         = var.dlp_sensor_status
  dsri                      = var.dsri
  interface                 = var.interface
  ips_sensor                = var.ips_sensor
  ips_sensor_status         = var.ips_sensor_status
  label                     = var.label
  logtraffic                = var.logtraffic
  policyid                  = var.policyid
  scan_botnet_connections   = var.scan_botnet_connections
  spamfilter_profile        = var.spamfilter_profile
  spamfilter_profile_status = var.spamfilter_profile_status
  status                    = var.status
  webfilter_profile         = var.webfilter_profile
  webfilter_profile_status  = var.webfilter_profile_status

  dynamic "dstaddr6" {
    for_each = var.dstaddr6
    content {
      name = dstaddr6.value["name"]
    }
  }

  dynamic "service6" {
    for_each = var.service6
    content {
      name = service6.value["name"]
    }
  }

  dynamic "srcaddr6" {
    for_each = var.srcaddr6
    content {
      name = srcaddr6.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "address_type" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.address_type
}

output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.application_list
}

output "application_list_status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.application_list_status
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.av_profile
}

output "av_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.av_profile_status
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.dlp_sensor
}

output "dlp_sensor_status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.dlp_sensor_status
}

output "dsri" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.dsri
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.id
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.ips_sensor
}

output "ips_sensor_status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.ips_sensor_status
}

output "label" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.label
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.logtraffic
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_interfacepolicy6.this.policyid
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.scan_botnet_connections
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.spamfilter_profile
}

output "spamfilter_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.spamfilter_profile_status
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.status
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.webfilter_profile
}

output "webfilter_profile_status" {
  description = "returns a string"
  value       = fortios_firewall_interfacepolicy6.this.webfilter_profile_status
}

output "this" {
  value = fortios_firewall_interfacepolicy6.this
}
```

[top](#index)