# panos_ethernet_interface

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_ethernet_interface" {
  source = "./modules/panos/r/panos_ethernet_interface"

  # adjust_tcp_mss - (optional) is a type of bool
  adjust_tcp_mss = null
  # aggregate_group - (optional) is a type of string
  aggregate_group = null
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
  # ipv4_mss_adjust - (optional) is a type of number
  ipv4_mss_adjust = null
  # ipv6_enabled - (optional) is a type of bool
  ipv6_enabled = null
  # ipv6_mss_adjust - (optional) is a type of number
  ipv6_mss_adjust = null
  # link_duplex - (optional) is a type of string
  link_duplex = null
  # link_speed - (optional) is a type of string
  link_speed = null
  # link_state - (optional) is a type of string
  link_state = null
  # lldp_enabled - (optional) is a type of bool
  lldp_enabled = null
  # lldp_profile - (optional) is a type of string
  lldp_profile = null
  # management_profile - (optional) is a type of string
  management_profile = null
  # mode - (required) is a type of string
  mode = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # netflow_profile - (optional) is a type of string
  netflow_profile = null
  # rx_policing_rate - (optional) is a type of number
  rx_policing_rate = null
  # static_ips - (optional) is a type of list of string
  static_ips = []
  # tx_policing_rate - (optional) is a type of number
  tx_policing_rate = null
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

variable "aggregate_group" {
  description = "(optional)"
  type        = string
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

variable "ipv6_mss_adjust" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "link_duplex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_speed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp_enabled" {
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
  description = "(required) - The interface mode (layer3, layer2, virtual-wire, tap, ha, decrypt-mirror, aggregate-group)"
  type        = string
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

variable "rx_policing_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "static_ips" {
  description = "(optional) - List of static IP addresses"
  type        = list(string)
  default     = null
}

variable "tx_policing_rate" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "panos_ethernet_interface" "this" {
  adjust_tcp_mss            = var.adjust_tcp_mss
  aggregate_group           = var.aggregate_group
  comment                   = var.comment
  create_dhcp_default_route = var.create_dhcp_default_route
  decrypt_forward           = var.decrypt_forward
  dhcp_default_route_metric = var.dhcp_default_route_metric
  dhcp_send_hostname_enable = var.dhcp_send_hostname_enable
  dhcp_send_hostname_value  = var.dhcp_send_hostname_value
  enable_dhcp               = var.enable_dhcp
  ipv4_mss_adjust           = var.ipv4_mss_adjust
  ipv6_enabled              = var.ipv6_enabled
  ipv6_mss_adjust           = var.ipv6_mss_adjust
  link_duplex               = var.link_duplex
  link_speed                = var.link_speed
  link_state                = var.link_state
  lldp_enabled              = var.lldp_enabled
  lldp_profile              = var.lldp_profile
  management_profile        = var.management_profile
  mode                      = var.mode
  mtu                       = var.mtu
  name                      = var.name
  netflow_profile           = var.netflow_profile
  rx_policing_rate          = var.rx_policing_rate
  static_ips                = var.static_ips
  tx_policing_rate          = var.tx_policing_rate
  vsys                      = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ethernet_interface.this.id
}

output "this" {
  value = panos_ethernet_interface.this
}
```

[top](#index)