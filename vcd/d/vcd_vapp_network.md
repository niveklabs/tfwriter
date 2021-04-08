# vcd_vapp_network

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/vcd/d/vcd_vapp_network"

  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - vApp network name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "vcd_vapp_network" "this" {
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vapp_name - (required) is a type of string
  vapp_name = var.vapp_name
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.description
}

output "dhcp_pool" {
  description = "returns a set of object"
  value       = data.vcd_vapp_network.this.dhcp_pool
}

output "dns1" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.dns1
}

output "dns2" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.dns2
}

output "dns_suffix" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.dns_suffix
}

output "gateway" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.gateway
}

output "guest_vlan_allowed" {
  description = "returns a bool"
  value       = data.vcd_vapp_network.this.guest_vlan_allowed
}

output "id" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.id
}

output "netmask" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.netmask
}

output "org_network_name" {
  description = "returns a string"
  value       = data.vcd_vapp_network.this.org_network_name
}

output "retain_ip_mac_enabled" {
  description = "returns a bool"
  value       = data.vcd_vapp_network.this.retain_ip_mac_enabled
}

output "static_ip_pool" {
  description = "returns a set of object"
  value       = data.vcd_vapp_network.this.static_ip_pool
}

output "this" {
  value = vcd_vapp_network.this
}
```

[top](#index)