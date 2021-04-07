# panos_panorama_tunnel_interface

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
module "panos_panorama_tunnel_interface" {
  source = "./modules/panos/r/panos_panorama_tunnel_interface"

  # comment - (optional) is a type of string
  comment = null
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
variable "comment" {
  description = "(optional)"
  type        = string
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
resource "panos_panorama_tunnel_interface" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # management_profile - (optional) is a type of string
  management_profile = var.management_profile
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # netflow_profile - (optional) is a type of string
  netflow_profile = var.netflow_profile
  # static_ips - (optional) is a type of list of string
  static_ips = var.static_ips
  # template - (required) is a type of string
  template = var.template
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_tunnel_interface.this.id
}

output "this" {
  value = panos_panorama_tunnel_interface.this
}
```

[top](#index)