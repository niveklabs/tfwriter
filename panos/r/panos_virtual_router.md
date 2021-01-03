# panos_virtual_router

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_virtual_router" {
  source = "./modules/panos/r/panos_virtual_router"

  # ebgp_dist - (optional) is a type of number
  ebgp_dist = null
  # ibgp_dist - (optional) is a type of number
  ibgp_dist = null
  # interfaces - (optional) is a type of list of string
  interfaces = []
  # name - (required) is a type of string
  name = null
  # ospf_ext_dist - (optional) is a type of number
  ospf_ext_dist = null
  # ospf_int_dist - (optional) is a type of number
  ospf_int_dist = null
  # ospfv3_ext_dist - (optional) is a type of number
  ospfv3_ext_dist = null
  # ospfv3_int_dist - (optional) is a type of number
  ospfv3_int_dist = null
  # rip_dist - (optional) is a type of number
  rip_dist = null
  # static_dist - (optional) is a type of number
  static_dist = null
  # static_ipv6_dist - (optional) is a type of number
  static_ipv6_dist = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "ebgp_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ibgp_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interfaces" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ospf_ext_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ospf_int_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ospfv3_ext_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ospfv3_int_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rip_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "static_dist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "static_ipv6_dist" {
  description = "(optional)"
  type        = number
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
resource "panos_virtual_router" "this" {
  ebgp_dist        = var.ebgp_dist
  ibgp_dist        = var.ibgp_dist
  interfaces       = var.interfaces
  name             = var.name
  ospf_ext_dist    = var.ospf_ext_dist
  ospf_int_dist    = var.ospf_int_dist
  ospfv3_ext_dist  = var.ospfv3_ext_dist
  ospfv3_int_dist  = var.ospfv3_int_dist
  rip_dist         = var.rip_dist
  static_dist      = var.static_dist
  static_ipv6_dist = var.static_ipv6_dist
  vsys             = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_virtual_router.this.id
}

output "interfaces" {
  description = "returns a list of string"
  value       = panos_virtual_router.this.interfaces
}

output "this" {
  value = panos_virtual_router.this
}
```

[top](#index)