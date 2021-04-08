# vcd_vapp_network

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_vapp_network" {
  source = "./modules/vcd/r/vcd_vapp_network"

  # description - (optional) is a type of string
  description = null
  # dns1 - (optional) is a type of string
  dns1 = null
  # dns2 - (optional) is a type of string
  dns2 = null
  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # gateway - (required) is a type of string
  gateway = null
  # guest_vlan_allowed - (optional) is a type of bool
  guest_vlan_allowed = null
  # name - (required) is a type of string
  name = null
  # netmask - (optional) is a type of string
  netmask = null
  # org - (optional) is a type of string
  org = null
  # org_network_name - (optional) is a type of string
  org_network_name = null
  # retain_ip_mac_enabled - (optional) is a type of bool
  retain_ip_mac_enabled = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null

  dhcp_pool = [{
    default_lease_time = null
    enabled            = null
    end_address        = null
    max_lease_time     = null
    start_address      = null
  }]

  static_ip_pool = [{
    end_address   = null
    start_address = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Optional description for the network"
  type        = string
  default     = null
}

variable "dns1" {
  description = "(optional) - Primary DNS server"
  type        = string
  default     = null
}

variable "dns2" {
  description = "(optional) - Secondary DNS server"
  type        = string
  default     = null
}

variable "dns_suffix" {
  description = "(optional) - DNS suffix"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(required) - Gateway of the network"
  type        = string
}

variable "guest_vlan_allowed" {
  description = "(optional) - True if Network allows guest VLAN tagging"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - vApp network name"
  type        = string
}

variable "netmask" {
  description = "(optional) - Netmask address for a subnet. Default is 255.255.255.0"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "org_network_name" {
  description = "(optional) - org network name to which vapp network is connected"
  type        = string
  default     = null
}

variable "retain_ip_mac_enabled" {
  description = "(optional) - Specifies whether the network resources such as IP/MAC of router will be retained across deployments. Default is false."
  type        = bool
  default     = null
}

variable "vapp_name" {
  description = "(required) - vApp to use"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "dhcp_pool" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_lease_time = number
      enabled            = bool
      end_address        = string
      max_lease_time     = number
      start_address      = string
    }
  ))
  default = []
}

variable "static_ip_pool" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      end_address   = string
      start_address = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp_network" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dns1 - (optional) is a type of string
  dns1 = var.dns1
  # dns2 - (optional) is a type of string
  dns2 = var.dns2
  # dns_suffix - (optional) is a type of string
  dns_suffix = var.dns_suffix
  # gateway - (required) is a type of string
  gateway = var.gateway
  # guest_vlan_allowed - (optional) is a type of bool
  guest_vlan_allowed = var.guest_vlan_allowed
  # name - (required) is a type of string
  name = var.name
  # netmask - (optional) is a type of string
  netmask = var.netmask
  # org - (optional) is a type of string
  org = var.org
  # org_network_name - (optional) is a type of string
  org_network_name = var.org_network_name
  # retain_ip_mac_enabled - (optional) is a type of bool
  retain_ip_mac_enabled = var.retain_ip_mac_enabled
  # vapp_name - (required) is a type of string
  vapp_name = var.vapp_name
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "dhcp_pool" {
    for_each = var.dhcp_pool
    content {
      # default_lease_time - (optional) is a type of number
      default_lease_time = dhcp_pool.value["default_lease_time"]
      # enabled - (optional) is a type of bool
      enabled = dhcp_pool.value["enabled"]
      # end_address - (optional) is a type of string
      end_address = dhcp_pool.value["end_address"]
      # max_lease_time - (optional) is a type of number
      max_lease_time = dhcp_pool.value["max_lease_time"]
      # start_address - (required) is a type of string
      start_address = dhcp_pool.value["start_address"]
    }
  }

  dynamic "static_ip_pool" {
    for_each = var.static_ip_pool
    content {
      # end_address - (required) is a type of string
      end_address = static_ip_pool.value["end_address"]
      # start_address - (required) is a type of string
      start_address = static_ip_pool.value["start_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vapp_network.this.id
}

output "this" {
  value = vcd_vapp_network.this
}
```

[top](#index)