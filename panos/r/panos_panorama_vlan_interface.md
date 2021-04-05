# panos_panorama_vlan_interface

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
module "panos_panorama_vlan_interface" {
  source = "./modules/panos/r/panos_panorama_vlan_interface"

  # adjust_tcp_mss - (optional) is a type of bool
  adjust_tcp_mss = null
  # comment - (optional) is a type of string
  comment = null
  # create_dhcp_default_route - (optional) is a type of bool
  create_dhcp_default_route = null
  # dhcp_default_route_metric - (optional) is a type of number
  dhcp_default_route_metric = null
  # enable_dhcp - (optional) is a type of bool
  enable_dhcp = null
  # ipv4_mss_adjust - (optional) is a type of number
  ipv4_mss_adjust = null
  # ipv6_mss_adjust - (optional) is a type of number
  ipv6_mss_adjust = null
  # management_profile - (optional) is a type of string
  management_profile = null
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

variable "dhcp_default_route_metric" {
  description = "(optional)"
  type        = number
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

variable "ipv6_mss_adjust" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "management_profile" {
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
resource "panos_panorama_vlan_interface" "this" {
  adjust_tcp_mss            = var.adjust_tcp_mss
  comment                   = var.comment
  create_dhcp_default_route = var.create_dhcp_default_route
  dhcp_default_route_metric = var.dhcp_default_route_metric
  enable_dhcp               = var.enable_dhcp
  ipv4_mss_adjust           = var.ipv4_mss_adjust
  ipv6_mss_adjust           = var.ipv6_mss_adjust
  management_profile        = var.management_profile
  mtu                       = var.mtu
  name                      = var.name
  netflow_profile           = var.netflow_profile
  static_ips                = var.static_ips
  template                  = var.template
  vsys                      = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_vlan_interface.this.id
}

output "this" {
  value = panos_panorama_vlan_interface.this
}
```

[top](#index)