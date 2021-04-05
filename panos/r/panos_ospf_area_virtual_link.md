# panos_ospf_area_virtual_link

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
module "panos_ospf_area_virtual_link" {
  source = "./modules/panos/r/panos_ospf_area_virtual_link"

  # auth_profile - (optional) is a type of string
  auth_profile = null
  # bfd_profile - (optional) is a type of string
  bfd_profile = null
  # dead_counts - (optional) is a type of number
  dead_counts = null
  # enable - (optional) is a type of bool
  enable = null
  # hello_interval - (optional) is a type of number
  hello_interval = null
  # name - (required) is a type of string
  name = null
  # neighbor_id - (required) is a type of string
  neighbor_id = null
  # ospf_area - (required) is a type of string
  ospf_area = null
  # retransmit_interval - (optional) is a type of number
  retransmit_interval = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # transit_area_id - (required) is a type of string
  transit_area_id = null
  # transit_delay - (optional) is a type of number
  transit_delay = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_profile" {
  description = "(optional) - Auth profile"
  type        = string
  default     = null
}

variable "bfd_profile" {
  description = "(optional) - BFD profile"
  type        = string
  default     = null
}

variable "dead_counts" {
  description = "(optional) - Dead counts"
  type        = number
  default     = null
}

variable "enable" {
  description = "(optional) - Enable"
  type        = bool
  default     = null
}

variable "hello_interval" {
  description = "(optional) - Hello interval in seconds"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "neighbor_id" {
  description = "(required) - Neighbor ID"
  type        = string
}

variable "ospf_area" {
  description = "(required) - The OSPF area name"
  type        = string
}

variable "retransmit_interval" {
  description = "(optional) - Retransmit interval in seconds"
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

variable "transit_area_id" {
  description = "(required) - Transit area ID"
  type        = string
}

variable "transit_delay" {
  description = "(optional) - Transit delay in seconds"
  type        = number
  default     = null
}

variable "virtual_router" {
  description = "(required) - The virtual router"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_ospf_area_virtual_link" "this" {
  auth_profile        = var.auth_profile
  bfd_profile         = var.bfd_profile
  dead_counts         = var.dead_counts
  enable              = var.enable
  hello_interval      = var.hello_interval
  name                = var.name
  neighbor_id         = var.neighbor_id
  ospf_area           = var.ospf_area
  retransmit_interval = var.retransmit_interval
  template            = var.template
  template_stack      = var.template_stack
  transit_area_id     = var.transit_area_id
  transit_delay       = var.transit_delay
  virtual_router      = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ospf_area_virtual_link.this.id
}

output "this" {
  value = panos_ospf_area_virtual_link.this
}
```

[top](#index)