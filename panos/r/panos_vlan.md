# panos_vlan

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
module "panos_vlan" {
  source = "./modules/panos/r/panos_vlan"

  # interfaces - (optional) is a type of set of string
  interfaces = []
  # name - (required) is a type of string
  name = null
  # vlan_interface - (optional) is a type of string
  vlan_interface = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "interfaces" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "vlan_interface" {
  description = "(optional)"
  type        = string
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
resource "panos_vlan" "this" {
  # interfaces - (optional) is a type of set of string
  interfaces = var.interfaces
  # name - (required) is a type of string
  name = var.name
  # vlan_interface - (optional) is a type of string
  vlan_interface = var.vlan_interface
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_vlan.this.id
}

output "interfaces" {
  description = "returns a set of string"
  value       = panos_vlan.this.interfaces
}

output "this" {
  value = panos_vlan.this
}
```

[top](#index)