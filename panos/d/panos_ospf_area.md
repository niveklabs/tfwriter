# panos_ospf_area

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
module "panos_ospf_area" {
  source = "./modules/panos/d/panos_ospf_area"

  # name - (required) is a type of string
  name = null
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
data "panos_ospf_area" "this" {
  name           = var.name
  template       = var.template
  template_stack = var.template_stack
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "accept_summary" {
  description = "returns a bool"
  value       = data.panos_ospf_area.this.accept_summary
}

output "advertise_metric" {
  description = "returns a number"
  value       = data.panos_ospf_area.this.advertise_metric
}

output "advertise_type" {
  description = "returns a string"
  value       = data.panos_ospf_area.this.advertise_type
}

output "default_route_advertise" {
  description = "returns a bool"
  value       = data.panos_ospf_area.this.default_route_advertise
}

output "ext_range" {
  description = "returns a list of object"
  value       = data.panos_ospf_area.this.ext_range
}

output "id" {
  description = "returns a string"
  value       = data.panos_ospf_area.this.id
}

output "range" {
  description = "returns a list of object"
  value       = data.panos_ospf_area.this.range
}

output "type" {
  description = "returns a string"
  value       = data.panos_ospf_area.this.type
}

output "this" {
  value = panos_ospf_area.this
}
```

[top](#index)