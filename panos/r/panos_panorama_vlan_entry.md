# panos_panorama_vlan_entry

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
module "panos_panorama_vlan_entry" {
  source = "./modules/panos/r/panos_panorama_vlan_entry"

  # interface - (required) is a type of string
  interface = null
  # mac_addresses - (optional) is a type of set of string
  mac_addresses = []
  # template - (required) is a type of string
  template = null
  # vlan - (required) is a type of string
  vlan = null
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}

variable "mac_addresses" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "vlan" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_vlan_entry" "this" {
  # interface - (required) is a type of string
  interface = var.interface
  # mac_addresses - (optional) is a type of set of string
  mac_addresses = var.mac_addresses
  # template - (required) is a type of string
  template = var.template
  # vlan - (required) is a type of string
  vlan = var.vlan
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_vlan_entry.this.id
}

output "live_mac_addresses" {
  description = "returns a set of string"
  value       = panos_panorama_vlan_entry.this.live_mac_addresses
}

output "this" {
  value = panos_panorama_vlan_entry.this
}
```

[top](#index)