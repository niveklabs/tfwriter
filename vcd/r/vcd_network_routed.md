# vcd_network_routed

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
module "vcd_network_routed" {
  source = "./modules/vcd/r/vcd_network_routed"

  # description - (optional) is a type of string
  description = null
  # dns1 - (optional) is a type of string
  dns1 = null
  # dns2 - (optional) is a type of string
  dns2 = null
  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # gateway - (optional) is a type of string
  gateway = null
  # interface_type - (optional) is a type of string
  interface_type = null
  # name - (required) is a type of string
  name = null
  # netmask - (optional) is a type of string
  netmask = null
  # org - (optional) is a type of string
  org = null
  # shared - (optional) is a type of bool
  shared = null
  # vdc - (optional) is a type of string
  vdc = null

  dhcp_pool = [{
    default_lease_time = null
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
  description = "(optional) - First DNS server to use"
  type        = string
  default     = null
}

variable "dns2" {
  description = "(optional) - Second DNS server to use"
  type        = string
  default     = null
}

variable "dns_suffix" {
  description = "(optional) - A FQDN for the virtual machines on this network"
  type        = string
  default     = null
}

variable "edge_gateway" {
  description = "(required) - The name of the edge gateway"
  type        = string
}

variable "gateway" {
  description = "(optional) - The gateway of this network"
  type        = string
  default     = null
}

variable "interface_type" {
  description = "(optional) - Which interface to use (one of `internal`, `subinterface`, `distributed`)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - A unique name for the network"
  type        = string
}

variable "netmask" {
  description = "(optional) - The netmask for the new network"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "shared" {
  description = "(optional) - Defines if this network is shared between multiple VDCs in the Org"
  type        = bool
  default     = null
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
resource "vcd_network_routed" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dns1 - (optional) is a type of string
  dns1 = var.dns1
  # dns2 - (optional) is a type of string
  dns2 = var.dns2
  # dns_suffix - (optional) is a type of string
  dns_suffix = var.dns_suffix
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # gateway - (optional) is a type of string
  gateway = var.gateway
  # interface_type - (optional) is a type of string
  interface_type = var.interface_type
  # name - (required) is a type of string
  name = var.name
  # netmask - (optional) is a type of string
  netmask = var.netmask
  # org - (optional) is a type of string
  org = var.org
  # shared - (optional) is a type of bool
  shared = var.shared
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "dhcp_pool" {
    for_each = var.dhcp_pool
    content {
      # end_address - (required) is a type of string
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
output "href" {
  description = "returns a string"
  value       = vcd_network_routed.this.href
}

output "id" {
  description = "returns a string"
  value       = vcd_network_routed.this.id
}

output "this" {
  value = vcd_network_routed.this
}
```

[top](#index)