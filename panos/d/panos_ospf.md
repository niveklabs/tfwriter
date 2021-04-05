# panos_ospf

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
module "panos_ospf" {
  source = "./modules/panos/d/panos_ospf"

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
data "panos_ospf" "this" {
  template       = var.template
  template_stack = var.template_stack
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "allow_redistribute_default_route" {
  description = "returns a bool"
  value       = data.panos_ospf.this.allow_redistribute_default_route
}

output "bfd_profile" {
  description = "returns a string"
  value       = data.panos_ospf.this.bfd_profile
}

output "enable" {
  description = "returns a bool"
  value       = data.panos_ospf.this.enable
}

output "enable_graceful_restart" {
  description = "returns a bool"
  value       = data.panos_ospf.this.enable_graceful_restart
}

output "grace_period" {
  description = "returns a number"
  value       = data.panos_ospf.this.grace_period
}

output "helper_enable" {
  description = "returns a bool"
  value       = data.panos_ospf.this.helper_enable
}

output "id" {
  description = "returns a string"
  value       = data.panos_ospf.this.id
}

output "lsa_interval" {
  description = "returns a number"
  value       = data.panos_ospf.this.lsa_interval
}

output "max_neighbor_restart_time" {
  description = "returns a number"
  value       = data.panos_ospf.this.max_neighbor_restart_time
}

output "reject_default_route" {
  description = "returns a bool"
  value       = data.panos_ospf.this.reject_default_route
}

output "rfc_1583" {
  description = "returns a bool"
  value       = data.panos_ospf.this.rfc_1583
}

output "router_id" {
  description = "returns a string"
  value       = data.panos_ospf.this.router_id
}

output "spf_calculation_delay" {
  description = "returns a number"
  value       = data.panos_ospf.this.spf_calculation_delay
}

output "strict_lsa_checking" {
  description = "returns a bool"
  value       = data.panos_ospf.this.strict_lsa_checking
}

output "this" {
  value = panos_ospf.this
}
```

[top](#index)