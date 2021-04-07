# panos_panorama_virtual_router_entry

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
module "panos_panorama_virtual_router_entry" {
  source = "./modules/panos/r/panos_panorama_virtual_router_entry"

  # interface - (required) is a type of string
  interface = null
  # template - (required) is a type of string
  template = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_virtual_router_entry" "this" {
  # interface - (required) is a type of string
  interface = var.interface
  # template - (required) is a type of string
  template = var.template
  # virtual_router - (required) is a type of string
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_virtual_router_entry.this.id
}

output "this" {
  value = panos_panorama_virtual_router_entry.this
}
```

[top](#index)