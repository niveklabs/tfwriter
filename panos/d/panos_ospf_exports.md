# panos_ospf_exports

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
module "panos_ospf_exports" {
  source = "./modules/panos/d/panos_ospf_exports"

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
  description = "(required) - The virtual router name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "panos_ospf_exports" "this" {
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
  value       = data.panos_ospf_exports.this.id
}

output "listing" {
  description = "returns a list of string"
  value       = data.panos_ospf_exports.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.panos_ospf_exports.this.total
}

output "this" {
  value = panos_ospf_exports.this
}
```

[top](#index)