# panos_ospf_auth_profiles

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
module "panos_ospf_auth_profiles" {
  source = "./modules/panos/d/panos_ospf_auth_profiles"

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
data "panos_ospf_auth_profiles" "this" {
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
  value       = data.panos_ospf_auth_profiles.this.id
}

output "listing" {
  description = "returns a list of string"
  value       = data.panos_ospf_auth_profiles.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.panos_ospf_auth_profiles.this.total
}

output "this" {
  value = panos_ospf_auth_profiles.this
}
```

[top](#index)