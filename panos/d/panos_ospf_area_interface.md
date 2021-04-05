# panos_ospf_area_interface

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/panos/d/panos_ospf_area_interface"

  # name - (required) is a type of string
  name = null
  # ospf_area - (required) is a type of string
  ospf_area = null
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
variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "ospf_area" {
  description = "(required) - The OSPF area name"
  type        = string
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
  description = "(required) - The virtual router"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "panos_ospf_area_interface" "this" {
  name           = var.name
  ospf_area      = var.ospf_area
  template       = var.template
  template_stack = var.template_stack
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "auth_profile" {
  description = "returns a string"
  value       = data.panos_ospf_area_interface.this.auth_profile
}

output "bfd_profile" {
  description = "returns a string"
  value       = data.panos_ospf_area_interface.this.bfd_profile
}

output "dead_counts" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.dead_counts
}

output "enable" {
  description = "returns a bool"
  value       = data.panos_ospf_area_interface.this.enable
}

output "grace_restart_delay" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.grace_restart_delay
}

output "hello_interval" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.hello_interval
}

output "id" {
  description = "returns a string"
  value       = data.panos_ospf_area_interface.this.id
}

output "link_type" {
  description = "returns a string"
  value       = data.panos_ospf_area_interface.this.link_type
}

output "metric" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.metric
}

output "neighbors" {
  description = "returns a set of string"
  value       = data.panos_ospf_area_interface.this.neighbors
}

output "passive" {
  description = "returns a bool"
  value       = data.panos_ospf_area_interface.this.passive
}

output "priority" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.priority
}

output "retransmit_interval" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.retransmit_interval
}

output "transit_delay" {
  description = "returns a number"
  value       = data.panos_ospf_area_interface.this.transit_delay
}

output "this" {
  value = panos_ospf_area_interface.this
}
```

[top](#index)