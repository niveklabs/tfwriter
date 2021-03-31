# vsphere_vnic

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_vnic" {
  source = "./modules/vsphere/r/vsphere_vnic"

  # distributed_port_group - (optional) is a type of string
  distributed_port_group = null
  # distributed_switch_port - (optional) is a type of string
  distributed_switch_port = null
  # host - (required) is a type of string
  host = null
  # mac - (optional) is a type of string
  mac = null
  # mtu - (optional) is a type of number
  mtu = null
  # netstack - (optional) is a type of string
  netstack = null
  # portgroup - (optional) is a type of string
  portgroup = null

  ipv4 = [{
    dhcp    = null
    gw      = null
    ip      = null
    netmask = null
  }]

  ipv6 = [{
    addresses  = []
    autoconfig = null
    dhcp       = null
    gw         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "distributed_port_group" {
  description = "(optional) - Key of the distributed portgroup the nic will connect to"
  type        = string
  default     = null
}

variable "distributed_switch_port" {
  description = "(optional) - UUID of the DVSwitch the nic will be attached to. Do not set if you set portgroup."
  type        = string
  default     = null
}

variable "host" {
  description = "(required) - ESX host the interface belongs to"
  type        = string
}

variable "mac" {
  description = "(optional) - MAC address of the interface."
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - MTU of the interface."
  type        = number
  default     = null
}

variable "netstack" {
  description = "(optional) - TCP/IP stack setting for this interface. Possible values are 'default', 'vmotion', 'provisioning'"
  type        = string
  default     = null
}

variable "portgroup" {
  description = "(optional) - portgroup to attach the nic to. Do not set if you set distributed_switch_port."
  type        = string
  default     = null
}

variable "ipv4" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dhcp    = bool
      gw      = string
      ip      = string
      netmask = string
    }
  ))
  default = []
}

variable "ipv6" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      addresses  = list(string)
      autoconfig = bool
      dhcp       = bool
      gw         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_vnic" "this" {
  distributed_port_group  = var.distributed_port_group
  distributed_switch_port = var.distributed_switch_port
  host                    = var.host
  mac                     = var.mac
  mtu                     = var.mtu
  netstack                = var.netstack
  portgroup               = var.portgroup

  dynamic "ipv4" {
    for_each = var.ipv4
    content {
      dhcp    = ipv4.value["dhcp"]
      gw      = ipv4.value["gw"]
      ip      = ipv4.value["ip"]
      netmask = ipv4.value["netmask"]
    }
  }

  dynamic "ipv6" {
    for_each = var.ipv6
    content {
      addresses  = ipv6.value["addresses"]
      autoconfig = ipv6.value["autoconfig"]
      dhcp       = ipv6.value["dhcp"]
      gw         = ipv6.value["gw"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_vnic.this.id
}

output "mac" {
  description = "returns a string"
  value       = vsphere_vnic.this.mac
}

output "mtu" {
  description = "returns a number"
  value       = vsphere_vnic.this.mtu
}

output "this" {
  value = vsphere_vnic.this
}
```

[top](#index)