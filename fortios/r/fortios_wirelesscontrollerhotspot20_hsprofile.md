# fortios_wirelesscontrollerhotspot20_hsprofile

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
module "fortios_wirelesscontrollerhotspot20_hsprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_hsprofile"

  # access_network_asra - (optional) is a type of string
  access_network_asra = null
  # access_network_esr - (optional) is a type of string
  access_network_esr = null
  # access_network_internet - (optional) is a type of string
  access_network_internet = null
  # access_network_type - (optional) is a type of string
  access_network_type = null
  # access_network_uesa - (optional) is a type of string
  access_network_uesa = null
  # anqp_domain_id - (optional) is a type of number
  anqp_domain_id = null
  # bss_transition - (optional) is a type of string
  bss_transition = null
  # conn_cap - (optional) is a type of string
  conn_cap = null
  # deauth_request_timeout - (optional) is a type of number
  deauth_request_timeout = null
  # dgaf - (optional) is a type of string
  dgaf = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # gas_comeback_delay - (optional) is a type of number
  gas_comeback_delay = null
  # gas_fragmentation_limit - (optional) is a type of number
  gas_fragmentation_limit = null
  # hessid - (optional) is a type of string
  hessid = null
  # ip_addr_type - (optional) is a type of string
  ip_addr_type = null
  # l2tif - (optional) is a type of string
  l2tif = null
  # n3gpp_plmn - (optional) is a type of string
  n3gpp_plmn = null
  # nai_realm - (optional) is a type of string
  nai_realm = null
  # name - (optional) is a type of string
  name = null
  # network_auth - (optional) is a type of string
  network_auth = null
  # oper_friendly_name - (optional) is a type of string
  oper_friendly_name = null
  # osu_ssid - (optional) is a type of string
  osu_ssid = null
  # pame_bi - (optional) is a type of string
  pame_bi = null
  # proxy_arp - (optional) is a type of string
  proxy_arp = null
  # qos_map - (optional) is a type of string
  qos_map = null
  # roaming_consortium - (optional) is a type of string
  roaming_consortium = null
  # venue_group - (optional) is a type of string
  venue_group = null
  # venue_name - (optional) is a type of string
  venue_name = null
  # venue_type - (optional) is a type of string
  venue_type = null
  # wan_metrics - (optional) is a type of string
  wan_metrics = null
  # wnm_sleep_mode - (optional) is a type of string
  wnm_sleep_mode = null

  osu_provider = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_network_asra" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_network_esr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_network_internet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_network_uesa" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anqp_domain_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bss_transition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conn_cap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deauth_request_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dgaf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gas_comeback_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gas_fragmentation_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hessid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_addr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "l2tif" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "n3gpp_plmn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nai_realm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oper_friendly_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "osu_ssid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pame_bi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_arp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_map" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roaming_consortium" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "venue_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "venue_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "venue_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wan_metrics" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wnm_sleep_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "osu_provider" {
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
resource "fortios_wirelesscontrollerhotspot20_hsprofile" "this" {
  # access_network_asra - (optional) is a type of string
  access_network_asra = var.access_network_asra
  # access_network_esr - (optional) is a type of string
  access_network_esr = var.access_network_esr
  # access_network_internet - (optional) is a type of string
  access_network_internet = var.access_network_internet
  # access_network_type - (optional) is a type of string
  access_network_type = var.access_network_type
  # access_network_uesa - (optional) is a type of string
  access_network_uesa = var.access_network_uesa
  # anqp_domain_id - (optional) is a type of number
  anqp_domain_id = var.anqp_domain_id
  # bss_transition - (optional) is a type of string
  bss_transition = var.bss_transition
  # conn_cap - (optional) is a type of string
  conn_cap = var.conn_cap
  # deauth_request_timeout - (optional) is a type of number
  deauth_request_timeout = var.deauth_request_timeout
  # dgaf - (optional) is a type of string
  dgaf = var.dgaf
  # domain_name - (optional) is a type of string
  domain_name = var.domain_name
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # gas_comeback_delay - (optional) is a type of number
  gas_comeback_delay = var.gas_comeback_delay
  # gas_fragmentation_limit - (optional) is a type of number
  gas_fragmentation_limit = var.gas_fragmentation_limit
  # hessid - (optional) is a type of string
  hessid = var.hessid
  # ip_addr_type - (optional) is a type of string
  ip_addr_type = var.ip_addr_type
  # l2tif - (optional) is a type of string
  l2tif = var.l2tif
  # n3gpp_plmn - (optional) is a type of string
  n3gpp_plmn = var.n3gpp_plmn
  # nai_realm - (optional) is a type of string
  nai_realm = var.nai_realm
  # name - (optional) is a type of string
  name = var.name
  # network_auth - (optional) is a type of string
  network_auth = var.network_auth
  # oper_friendly_name - (optional) is a type of string
  oper_friendly_name = var.oper_friendly_name
  # osu_ssid - (optional) is a type of string
  osu_ssid = var.osu_ssid
  # pame_bi - (optional) is a type of string
  pame_bi = var.pame_bi
  # proxy_arp - (optional) is a type of string
  proxy_arp = var.proxy_arp
  # qos_map - (optional) is a type of string
  qos_map = var.qos_map
  # roaming_consortium - (optional) is a type of string
  roaming_consortium = var.roaming_consortium
  # venue_group - (optional) is a type of string
  venue_group = var.venue_group
  # venue_name - (optional) is a type of string
  venue_name = var.venue_name
  # venue_type - (optional) is a type of string
  venue_type = var.venue_type
  # wan_metrics - (optional) is a type of string
  wan_metrics = var.wan_metrics
  # wnm_sleep_mode - (optional) is a type of string
  wnm_sleep_mode = var.wnm_sleep_mode

  dynamic "osu_provider" {
    for_each = var.osu_provider
    content {
      # name - (optional) is a type of string
      name = osu_provider.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_network_asra" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.access_network_asra
}

output "access_network_esr" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.access_network_esr
}

output "access_network_internet" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.access_network_internet
}

output "access_network_type" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.access_network_type
}

output "access_network_uesa" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.access_network_uesa
}

output "anqp_domain_id" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.anqp_domain_id
}

output "bss_transition" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.bss_transition
}

output "conn_cap" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.conn_cap
}

output "deauth_request_timeout" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.deauth_request_timeout
}

output "dgaf" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.dgaf
}

output "domain_name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.domain_name
}

output "gas_comeback_delay" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.gas_comeback_delay
}

output "gas_fragmentation_limit" {
  description = "returns a number"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.gas_fragmentation_limit
}

output "hessid" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.hessid
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.id
}

output "ip_addr_type" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.ip_addr_type
}

output "l2tif" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.l2tif
}

output "n3gpp_plmn" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.n3gpp_plmn
}

output "nai_realm" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.nai_realm
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.name
}

output "network_auth" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.network_auth
}

output "oper_friendly_name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.oper_friendly_name
}

output "osu_ssid" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.osu_ssid
}

output "pame_bi" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.pame_bi
}

output "proxy_arp" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.proxy_arp
}

output "qos_map" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.qos_map
}

output "roaming_consortium" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.roaming_consortium
}

output "venue_group" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.venue_group
}

output "venue_name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.venue_name
}

output "venue_type" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.venue_type
}

output "wan_metrics" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.wan_metrics
}

output "wnm_sleep_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_hsprofile.this.wnm_sleep_mode
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_hsprofile.this
}
```

[top](#index)