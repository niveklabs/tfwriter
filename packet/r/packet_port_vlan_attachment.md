# packet_port_vlan_attachment

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_port_vlan_attachment" {
  source = "./modules/packet/r/packet_port_vlan_attachment"

  # device_id - (required) is a type of string
  device_id = null
  # force_bond - (optional) is a type of bool
  force_bond = null
  # native - (optional) is a type of bool
  native = null
  # port_name - (required) is a type of string
  port_name = null
  # vlan_vnid - (required) is a type of number
  vlan_vnid = null
}
```

[top](#index)

### Variables

```terraform
variable "device_id" {
  description = "(required)"
  type        = string
}

variable "force_bond" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "native" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "port_name" {
  description = "(required)"
  type        = string
}

variable "vlan_vnid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "packet_port_vlan_attachment" "this" {
  # device_id - (required) is a type of string
  device_id = var.device_id
  # force_bond - (optional) is a type of bool
  force_bond = var.force_bond
  # native - (optional) is a type of bool
  native = var.native
  # port_name - (required) is a type of string
  port_name = var.port_name
  # vlan_vnid - (required) is a type of number
  vlan_vnid = var.vlan_vnid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = packet_port_vlan_attachment.this.id
}

output "port_id" {
  description = "returns a string"
  value       = packet_port_vlan_attachment.this.port_id
}

output "vlan_id" {
  description = "returns a string"
  value       = packet_port_vlan_attachment.this.vlan_id
}

output "this" {
  value = packet_port_vlan_attachment.this
}
```

[top](#index)