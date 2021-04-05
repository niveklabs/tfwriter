# panos_panorama_aggregate_interface

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_aggregate_interface" {
  source = "./modules/panos/r/panos_panorama_aggregate_interface"

  # adjust_tcp_mss - (optional) is a type of bool
  adjust_tcp_mss = null
  # comment - (optional) is a type of string
  comment = null
  # create_dhcp_default_route - (optional) is a type of bool
  create_dhcp_default_route = null
  # decrypt_forward - (optional) is a type of bool
  decrypt_forward = null
  # dhcp_default_route_metric - (optional) is a type of number
  dhcp_default_route_metric = null
  # dhcp_send_hostname_enable - (optional) is a type of bool
  dhcp_send_hostname_enable = null
  # dhcp_send_hostname_value - (optional) is a type of string
  dhcp_send_hostname_value = null
  # enable_dhcp - (optional) is a type of bool
  enable_dhcp = null
  # enable_untagged_subinterface - (optional) is a type of bool
  enable_untagged_subinterface = null
  # ipv4_mss_adjust - (optional) is a type of number
  ipv4_mss_adjust = null
  # ipv6_enabled - (optional) is a type of bool
  ipv6_enabled = null
  # ipv6_interface_id - (optional) is a type of string
  ipv6_interface_id = null
  # ipv6_mss_adjust - (optional) is a type of number
  ipv6_mss_adjust = null
  # lacp_enable - (optional) is a type of bool
  lacp_enable = null
  # lacp_fast_failover - (optional) is a type of bool
  lacp_fast_failover = null
  # lacp_ha_enable_same_system_mac - (optional) is a type of bool
  lacp_ha_enable_same_system_mac = null
  # lacp_ha_passive_pre_negotiation - (optional) is a type of bool
  lacp_ha_passive_pre_negotiation = null
  # lacp_ha_same_system_mac_address - (optional) is a type of string
  lacp_ha_same_system_mac_address = null
  # lacp_max_ports - (optional) is a type of number
  lacp_max_ports = null
  # lacp_mode - (optional) is a type of string
  lacp_mode = null
  # lacp_system_priority - (optional) is a type of number
  lacp_system_priority = null
  # lacp_transmission_rate - (optional) is a type of string
  lacp_transmission_rate = null
  # lldp_enable - (optional) is a type of bool
  lldp_enable = null
  # lldp_ha_passive_pre_negotiation - (optional) is a type of bool
  lldp_ha_passive_pre_negotiation = null
  # lldp_profile - (optional) is a type of string
  lldp_profile = null
  # management_profile - (optional) is a type of string
  management_profile = null
  # mode - (optional) is a type of string
  mode = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # netflow_profile - (optional) is a type of string
  netflow_profile = null
  # static_ips - (optional) is a type of list of string
  static_ips = []
  # template - (required) is a type of string
  template = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "adjust_tcp_mss" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "create_dhcp_default_route" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "decrypt_forward" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dhcp_default_route_metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dhcp_send_hostname_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dhcp_send_hostname_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_untagged_subinterface" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipv4_mss_adjust" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipv6_interface_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_mss_adjust" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lacp_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lacp_fast_failover" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lacp_ha_enable_same_system_mac" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lacp_ha_passive_pre_negotiation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lacp_ha_same_system_mac_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lacp_max_ports" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lacp_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lacp_system_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lacp_transmission_rate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lldp_ha_passive_pre_negotiation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lldp_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "netflow_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "static_ips" {
  description = "(optional) - List of static IP addresses"
  type        = list(string)
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_aggregate_interface" "this" {
  adjust_tcp_mss                  = var.adjust_tcp_mss
  comment                         = var.comment
  create_dhcp_default_route       = var.create_dhcp_default_route
  decrypt_forward                 = var.decrypt_forward
  dhcp_default_route_metric       = var.dhcp_default_route_metric
  dhcp_send_hostname_enable       = var.dhcp_send_hostname_enable
  dhcp_send_hostname_value        = var.dhcp_send_hostname_value
  enable_dhcp                     = var.enable_dhcp
  enable_untagged_subinterface    = var.enable_untagged_subinterface
  ipv4_mss_adjust                 = var.ipv4_mss_adjust
  ipv6_enabled                    = var.ipv6_enabled
  ipv6_interface_id               = var.ipv6_interface_id
  ipv6_mss_adjust                 = var.ipv6_mss_adjust
  lacp_enable                     = var.lacp_enable
  lacp_fast_failover              = var.lacp_fast_failover
  lacp_ha_enable_same_system_mac  = var.lacp_ha_enable_same_system_mac
  lacp_ha_passive_pre_negotiation = var.lacp_ha_passive_pre_negotiation
  lacp_ha_same_system_mac_address = var.lacp_ha_same_system_mac_address
  lacp_max_ports                  = var.lacp_max_ports
  lacp_mode                       = var.lacp_mode
  lacp_system_priority            = var.lacp_system_priority
  lacp_transmission_rate          = var.lacp_transmission_rate
  lldp_enable                     = var.lldp_enable
  lldp_ha_passive_pre_negotiation = var.lldp_ha_passive_pre_negotiation
  lldp_profile                    = var.lldp_profile
  management_profile              = var.management_profile
  mode                            = var.mode
  mtu                             = var.mtu
  name                            = var.name
  netflow_profile                 = var.netflow_profile
  static_ips                      = var.static_ips
  template                        = var.template
  vsys                            = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_aggregate_interface.this.id
}

output "this" {
  value = panos_panorama_aggregate_interface.this
}
```

[top](#index)