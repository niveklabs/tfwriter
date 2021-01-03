# fortios_firewall_profilegroup

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
module "fortios_firewall_profilegroup" {
  source = "./modules/fortios/r/fortios_firewall_profilegroup"

  # application_list - (optional) is a type of string
  application_list = null
  # av_profile - (optional) is a type of string
  av_profile = null
  # dlp_sensor - (optional) is a type of string
  dlp_sensor = null
  # dnsfilter_profile - (optional) is a type of string
  dnsfilter_profile = null
  # icap_profile - (optional) is a type of string
  icap_profile = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # name - (required) is a type of string
  name = null
  # profile_protocol_options - (optional) is a type of string
  profile_protocol_options = null
  # spamfilter_profile - (optional) is a type of string
  spamfilter_profile = null
  # ssh_filter_profile - (optional) is a type of string
  ssh_filter_profile = null
  # ssl_ssh_profile - (optional) is a type of string
  ssl_ssh_profile = null
  # voip_profile - (optional) is a type of string
  voip_profile = null
  # waf_profile - (optional) is a type of string
  waf_profile = null
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null
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

variable "av_profile" {
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

variable "icap_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_sensor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "profile_protocol_options" {
  description = "(optional)"
  type        = string
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

variable "voip_profile" {
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
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_profilegroup" "this" {
  application_list         = var.application_list
  av_profile               = var.av_profile
  dlp_sensor               = var.dlp_sensor
  dnsfilter_profile        = var.dnsfilter_profile
  icap_profile             = var.icap_profile
  ips_sensor               = var.ips_sensor
  name                     = var.name
  profile_protocol_options = var.profile_protocol_options
  spamfilter_profile       = var.spamfilter_profile
  ssh_filter_profile       = var.ssh_filter_profile
  ssl_ssh_profile          = var.ssl_ssh_profile
  voip_profile             = var.voip_profile
  waf_profile              = var.waf_profile
  webfilter_profile        = var.webfilter_profile
}
```

[top](#index)

### Outputs

```terraform
output "application_list" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.application_list
}

output "av_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.av_profile
}

output "dlp_sensor" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.dlp_sensor
}

output "dnsfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.dnsfilter_profile
}

output "icap_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.icap_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.id
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.ips_sensor
}

output "profile_protocol_options" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.profile_protocol_options
}

output "spamfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.spamfilter_profile
}

output "ssh_filter_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.ssh_filter_profile
}

output "ssl_ssh_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.ssl_ssh_profile
}

output "voip_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.voip_profile
}

output "waf_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.waf_profile
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_firewall_profilegroup.this.webfilter_profile
}

output "this" {
  value = fortios_firewall_profilegroup.this
}
```

[top](#index)