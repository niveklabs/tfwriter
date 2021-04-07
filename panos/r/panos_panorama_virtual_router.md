# panos_panorama_virtual_router

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
module "panos_panorama_virtual_router" {
  source = "./modules/panos/r/panos_panorama_virtual_router"

  # ebgp_dist - (optional) is a type of number
  ebgp_dist = null
  # ecmp_hash_seed - (optional) is a type of number
  ecmp_hash_seed = null
  # ecmp_hash_source_only - (optional) is a type of bool
  ecmp_hash_source_only = null
  # ecmp_hash_use_port - (optional) is a type of bool
  ecmp_hash_use_port = null
  # ecmp_load_balance_method - (optional) is a type of string
  ecmp_load_balance_method = null
  # ecmp_max_path - (optional) is a type of number
  ecmp_max_path = null
  # ecmp_strict_source_path - (optional) is a type of bool
  ecmp_strict_source_path = null
  # ecmp_symmetric_return - (optional) is a type of bool
  ecmp_symmetric_return = null
  # ecmp_weighted_round_robin_interfaces - (optional) is a type of map of number
  ecmp_weighted_round_robin_interfaces = {}
  # enable_ecmp - (optional) is a type of bool
  enable_ecmp = null
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
  # template - (required) is a type of string
  template = null
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

variable "ecmp_hash_seed" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ecmp_hash_source_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ecmp_hash_use_port" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ecmp_load_balance_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ecmp_max_path" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ecmp_strict_source_path" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ecmp_symmetric_return" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ecmp_weighted_round_robin_interfaces" {
  description = "(optional)"
  type        = map(number)
  default     = null
}

variable "enable_ecmp" {
  description = "(optional)"
  type        = bool
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
resource "panos_panorama_virtual_router" "this" {
  # ebgp_dist - (optional) is a type of number
  ebgp_dist = var.ebgp_dist
  # ecmp_hash_seed - (optional) is a type of number
  ecmp_hash_seed = var.ecmp_hash_seed
  # ecmp_hash_source_only - (optional) is a type of bool
  ecmp_hash_source_only = var.ecmp_hash_source_only
  # ecmp_hash_use_port - (optional) is a type of bool
  ecmp_hash_use_port = var.ecmp_hash_use_port
  # ecmp_load_balance_method - (optional) is a type of string
  ecmp_load_balance_method = var.ecmp_load_balance_method
  # ecmp_max_path - (optional) is a type of number
  ecmp_max_path = var.ecmp_max_path
  # ecmp_strict_source_path - (optional) is a type of bool
  ecmp_strict_source_path = var.ecmp_strict_source_path
  # ecmp_symmetric_return - (optional) is a type of bool
  ecmp_symmetric_return = var.ecmp_symmetric_return
  # ecmp_weighted_round_robin_interfaces - (optional) is a type of map of number
  ecmp_weighted_round_robin_interfaces = var.ecmp_weighted_round_robin_interfaces
  # enable_ecmp - (optional) is a type of bool
  enable_ecmp = var.enable_ecmp
  # ibgp_dist - (optional) is a type of number
  ibgp_dist = var.ibgp_dist
  # interfaces - (optional) is a type of list of string
  interfaces = var.interfaces
  # name - (required) is a type of string
  name = var.name
  # ospf_ext_dist - (optional) is a type of number
  ospf_ext_dist = var.ospf_ext_dist
  # ospf_int_dist - (optional) is a type of number
  ospf_int_dist = var.ospf_int_dist
  # ospfv3_ext_dist - (optional) is a type of number
  ospfv3_ext_dist = var.ospfv3_ext_dist
  # ospfv3_int_dist - (optional) is a type of number
  ospfv3_int_dist = var.ospfv3_int_dist
  # rip_dist - (optional) is a type of number
  rip_dist = var.rip_dist
  # static_dist - (optional) is a type of number
  static_dist = var.static_dist
  # static_ipv6_dist - (optional) is a type of number
  static_ipv6_dist = var.static_ipv6_dist
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
  value       = panos_panorama_virtual_router.this.id
}

output "interfaces" {
  description = "returns a list of string"
  value       = panos_panorama_virtual_router.this.interfaces
}

output "this" {
  value = panos_panorama_virtual_router.this
}
```

[top](#index)