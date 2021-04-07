# panos_panorama_bgp_dampening_profile

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
module "panos_panorama_bgp_dampening_profile" {
  source = "./modules/panos/r/panos_panorama_bgp_dampening_profile"

  # cutoff - (optional) is a type of number
  cutoff = null
  # decay_half_life_reachable - (optional) is a type of number
  decay_half_life_reachable = null
  # decay_half_life_unreachable - (optional) is a type of number
  decay_half_life_unreachable = null
  # enable - (optional) is a type of bool
  enable = null
  # max_hold_time - (optional) is a type of number
  max_hold_time = null
  # name - (required) is a type of string
  name = null
  # reuse - (optional) is a type of number
  reuse = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "cutoff" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "decay_half_life_reachable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "decay_half_life_unreachable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_hold_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "reuse" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_bgp_dampening_profile" "this" {
  # cutoff - (optional) is a type of number
  cutoff = var.cutoff
  # decay_half_life_reachable - (optional) is a type of number
  decay_half_life_reachable = var.decay_half_life_reachable
  # decay_half_life_unreachable - (optional) is a type of number
  decay_half_life_unreachable = var.decay_half_life_unreachable
  # enable - (optional) is a type of bool
  enable = var.enable
  # max_hold_time - (optional) is a type of number
  max_hold_time = var.max_hold_time
  # name - (required) is a type of string
  name = var.name
  # reuse - (optional) is a type of number
  reuse = var.reuse
  # template - (optional) is a type of string
  template = var.template
  # template_stack - (optional) is a type of string
  template_stack = var.template_stack
  # virtual_router - (required) is a type of string
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_bgp_dampening_profile.this.id
}

output "this" {
  value = panos_panorama_bgp_dampening_profile.this
}
```

[top](#index)