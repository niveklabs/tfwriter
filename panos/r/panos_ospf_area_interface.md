# panos_ospf_area_interface

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
module "panos_ospf_area_interface" {
  source = "./modules/panos/r/panos_ospf_area_interface"

  # auth_profile - (optional) is a type of string
  auth_profile = null
  # bfd_profile - (optional) is a type of string
  bfd_profile = null
  # dead_counts - (optional) is a type of number
  dead_counts = null
  # enable - (optional) is a type of bool
  enable = null
  # grace_restart_delay - (optional) is a type of number
  grace_restart_delay = null
  # hello_interval - (optional) is a type of number
  hello_interval = null
  # link_type - (optional) is a type of string
  link_type = null
  # metric - (optional) is a type of number
  metric = null
  # name - (required) is a type of string
  name = null
  # neighbors - (optional) is a type of set of string
  neighbors = []
  # ospf_area - (required) is a type of string
  ospf_area = null
  # passive - (optional) is a type of bool
  passive = null
  # priority - (optional) is a type of number
  priority = null
  # retransmit_interval - (optional) is a type of number
  retransmit_interval = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
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

variable "grace_restart_delay" {
  description = "(optional) - Graceful restart hello delay in seconds"
  type        = number
  default     = null
}

variable "hello_interval" {
  description = "(optional) - Hello interval in seconds"
  type        = number
  default     = null
}

variable "link_type" {
  description = "(optional) - Link type"
  type        = string
  default     = null
}

variable "metric" {
  description = "(optional) - Metric"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "neighbors" {
  description = "(optional) - (p2mp) List of neighbors"
  type        = set(string)
  default     = null
}

variable "ospf_area" {
  description = "(required) - The OSPF area name"
  type        = string
}

variable "passive" {
  description = "(optional) - Passive"
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional) - Priority"
  type        = number
  default     = null
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
resource "panos_ospf_area_interface" "this" {
  auth_profile        = var.auth_profile
  bfd_profile         = var.bfd_profile
  dead_counts         = var.dead_counts
  enable              = var.enable
  grace_restart_delay = var.grace_restart_delay
  hello_interval      = var.hello_interval
  link_type           = var.link_type
  metric              = var.metric
  name                = var.name
  neighbors           = var.neighbors
  ospf_area           = var.ospf_area
  passive             = var.passive
  priority            = var.priority
  retransmit_interval = var.retransmit_interval
  template            = var.template
  template_stack      = var.template_stack
  transit_delay       = var.transit_delay
  virtual_router      = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ospf_area_interface.this.id
}

output "this" {
  value = panos_ospf_area_interface.this
}
```

[top](#index)