# panos_ospf_area_virtual_link

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
module "panos_ospf_area_virtual_link" {
  source = "./modules/panos/d/panos_ospf_area_virtual_link"

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
data "panos_ospf_area_virtual_link" "this" {
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
  value       = data.panos_ospf_area_virtual_link.this.auth_profile
}

output "bfd_profile" {
  description = "returns a string"
  value       = data.panos_ospf_area_virtual_link.this.bfd_profile
}

output "dead_counts" {
  description = "returns a number"
  value       = data.panos_ospf_area_virtual_link.this.dead_counts
}

output "enable" {
  description = "returns a bool"
  value       = data.panos_ospf_area_virtual_link.this.enable
}

output "hello_interval" {
  description = "returns a number"
  value       = data.panos_ospf_area_virtual_link.this.hello_interval
}

output "id" {
  description = "returns a string"
  value       = data.panos_ospf_area_virtual_link.this.id
}

output "neighbor_id" {
  description = "returns a string"
  value       = data.panos_ospf_area_virtual_link.this.neighbor_id
}

output "retransmit_interval" {
  description = "returns a number"
  value       = data.panos_ospf_area_virtual_link.this.retransmit_interval
}

output "transit_area_id" {
  description = "returns a string"
  value       = data.panos_ospf_area_virtual_link.this.transit_area_id
}

output "transit_delay" {
  description = "returns a number"
  value       = data.panos_ospf_area_virtual_link.this.transit_delay
}

output "this" {
  value = panos_ospf_area_virtual_link.this
}
```

[top](#index)