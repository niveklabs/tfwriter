# opennebula_virtual_network

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_virtual_network" {
  source = "./modules/opennebula/r/opennebula_virtual_network"

  # automatic_vlan_id - (optional) is a type of bool
  automatic_vlan_id = null
  # bridge - (optional) is a type of string
  bridge = null
  # clusters - (optional) is a type of list of number
  clusters = []
  # description - (optional) is a type of string
  description = null
  # dns - (optional) is a type of string
  dns = null
  # gateway - (optional) is a type of string
  gateway = null
  # group - (optional) is a type of string
  group = null
  # guest_mtu - (optional) is a type of number
  guest_mtu = null
  # hold_size - (optional) is a type of number
  hold_size = null
  # ip_hold - (optional) is a type of string
  ip_hold = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # network_mask - (optional) is a type of string
  network_mask = null
  # permissions - (optional) is a type of string
  permissions = null
  # physical_device - (optional) is a type of string
  physical_device = null
  # reservation_size - (optional) is a type of number
  reservation_size = null
  # reservation_vnet - (optional) is a type of number
  reservation_vnet = null
  # security_groups - (optional) is a type of list of number
  security_groups = []
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
  # vlan_id - (optional) is a type of string
  vlan_id = null

  ar = [{
    ar_type       = null
    global_prefix = null
    ip4           = null
    ip6           = null
    mac           = null
    prefix_length = null
    size          = null
    ula_prefix    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "automatic_vlan_id" {
  description = "(optional) - If set, let OpenNebula to attribute VLAN ID"
  type        = bool
  default     = null
}

variable "bridge" {
  description = "(optional) - Name of the bridge interface to which the vnet should be associated"
  type        = string
  default     = null
}

variable "clusters" {
  description = "(optional) - List of cluster IDs hosting the virtual Network, if not set it uses the default cluster"
  type        = list(number)
  default     = null
}

variable "description" {
  description = "(optional) - Description of the vnet, in OpenNebula's XML or String format"
  type        = string
  default     = null
}

variable "dns" {
  description = "(optional) - DNS IP if necessary"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(optional) - Gateway IP if necessary"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional) - Name of the Group that onws the Virtual Network, If empty, it uses caller group"
  type        = string
  default     = null
}

variable "guest_mtu" {
  description = "(optional) - MTU of the Guest interface. Must be lower or equal to 'mtu' (defaut: 1500)"
  type        = number
  default     = null
}

variable "hold_size" {
  description = "(optional) - Carve a network reservation of this size from the reservation starting from `ip_hold`"
  type        = number
  default     = null
}

variable "ip_hold" {
  description = "(optional) - Start IP of the range to be held"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - MTU of the vnet (defaut: 1500)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the vnet"
  type        = string
}

variable "network_mask" {
  description = "(optional) - Network Mask"
  type        = string
  default     = null
}

variable "permissions" {
  description = "(optional) - Permissions for the vnet (in Unix format, owner-group-other, use-manage-admin)"
  type        = string
  default     = null
}

variable "physical_device" {
  description = "(optional) - Name of the physical device to which the vnet should be associated"
  type        = string
  default     = null
}

variable "reservation_size" {
  description = "(optional) - Reserve this many IPs from reservation_vnet"
  type        = number
  default     = null
}

variable "reservation_vnet" {
  description = "(optional) - Create a reservation from this VNET ID"
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(optional) - List of Security Group IDs to be applied to the VNET"
  type        = list(number)
  default     = null
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - Type of the Virtual Network: dummy, bridge, fw, ebtables, 802.1Q, vxlan, ovswitch. Default is 'bridge'"
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional) - VLAN ID. Only if 'Type' is : 802.1Q, vxlan or ovswich and if 'automatic_vlan_id' is not set"
  type        = string
  default     = null
}

variable "ar" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ar_type       = string
      global_prefix = string
      ip4           = string
      ip6           = string
      mac           = string
      prefix_length = string
      size          = number
      ula_prefix    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_virtual_network" "this" {
  # automatic_vlan_id - (optional) is a type of bool
  automatic_vlan_id = var.automatic_vlan_id
  # bridge - (optional) is a type of string
  bridge = var.bridge
  # clusters - (optional) is a type of list of number
  clusters = var.clusters
  # description - (optional) is a type of string
  description = var.description
  # dns - (optional) is a type of string
  dns = var.dns
  # gateway - (optional) is a type of string
  gateway = var.gateway
  # group - (optional) is a type of string
  group = var.group
  # guest_mtu - (optional) is a type of number
  guest_mtu = var.guest_mtu
  # hold_size - (optional) is a type of number
  hold_size = var.hold_size
  # ip_hold - (optional) is a type of string
  ip_hold = var.ip_hold
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # network_mask - (optional) is a type of string
  network_mask = var.network_mask
  # permissions - (optional) is a type of string
  permissions = var.permissions
  # physical_device - (optional) is a type of string
  physical_device = var.physical_device
  # reservation_size - (optional) is a type of number
  reservation_size = var.reservation_size
  # reservation_vnet - (optional) is a type of number
  reservation_vnet = var.reservation_vnet
  # security_groups - (optional) is a type of list of number
  security_groups = var.security_groups
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type
  # vlan_id - (optional) is a type of string
  vlan_id = var.vlan_id

  dynamic "ar" {
    for_each = var.ar
    content {
      # ar_type - (optional) is a type of string
      ar_type = ar.value["ar_type"]
      # global_prefix - (optional) is a type of string
      global_prefix = ar.value["global_prefix"]
      # ip4 - (optional) is a type of string
      ip4 = ar.value["ip4"]
      # ip6 - (optional) is a type of string
      ip6 = ar.value["ip6"]
      # mac - (optional) is a type of string
      mac = ar.value["mac"]
      # prefix_length - (optional) is a type of string
      prefix_length = ar.value["prefix_length"]
      # size - (required) is a type of number
      size = ar.value["size"]
      # ula_prefix - (optional) is a type of string
      ula_prefix = ar.value["ula_prefix"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "automatic_vlan_id" {
  description = "returns a bool"
  value       = opennebula_virtual_network.this.automatic_vlan_id
}

output "bridge" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.bridge
}

output "clusters" {
  description = "returns a list of number"
  value       = opennebula_virtual_network.this.clusters
}

output "description" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.description
}

output "dns" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.dns
}

output "gateway" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.gateway
}

output "gid" {
  description = "returns a number"
  value       = opennebula_virtual_network.this.gid
}

output "gname" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.gname
}

output "hold_size" {
  description = "returns a number"
  value       = opennebula_virtual_network.this.hold_size
}

output "id" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.id
}

output "ip_hold" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.ip_hold
}

output "network_mask" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.network_mask
}

output "permissions" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.permissions
}

output "physical_device" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.physical_device
}

output "reservation_size" {
  description = "returns a number"
  value       = opennebula_virtual_network.this.reservation_size
}

output "reservation_vnet" {
  description = "returns a number"
  value       = opennebula_virtual_network.this.reservation_vnet
}

output "security_groups" {
  description = "returns a list of number"
  value       = opennebula_virtual_network.this.security_groups
}

output "uid" {
  description = "returns a number"
  value       = opennebula_virtual_network.this.uid
}

output "uname" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.uname
}

output "vlan_id" {
  description = "returns a string"
  value       = opennebula_virtual_network.this.vlan_id
}

output "this" {
  value = opennebula_virtual_network.this
}
```

[top](#index)