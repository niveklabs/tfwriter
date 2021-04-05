# panos_ospf_area_virtual_links

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
module "panos_ospf_area_virtual_links" {
  source = "./modules/panos/d/panos_ospf_area_virtual_links"

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
  description = "(required) - The virtual router name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "panos_ospf_area_virtual_links" "this" {
  ospf_area      = var.ospf_area
  template       = var.template
  template_stack = var.template_stack
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.panos_ospf_area_virtual_links.this.id
}

output "listing" {
  description = "returns a list of string"
  value       = data.panos_ospf_area_virtual_links.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.panos_ospf_area_virtual_links.this.total
}

output "this" {
  value = panos_ospf_area_virtual_links.this
}
```

[top](#index)