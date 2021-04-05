# panos_panorama_template_stack

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
module "panos_panorama_template_stack" {
  source = "./modules/panos/r/panos_panorama_template_stack"

  # default_vsys - (optional) is a type of string
  default_vsys = null
  # description - (optional) is a type of string
  description = null
  # devices - (optional) is a type of list of string
  devices = []
  # name - (required) is a type of string
  name = null
  # templates - (optional) is a type of list of string
  templates = []
}
```

[top](#index)

### Variables

```terraform
variable "default_vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "devices" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "templates" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_template_stack" "this" {
  default_vsys = var.default_vsys
  description  = var.description
  devices      = var.devices
  name         = var.name
  templates    = var.templates
}
```

[top](#index)

### Outputs

```terraform
output "devices" {
  description = "returns a list of string"
  value       = panos_panorama_template_stack.this.devices
}

output "id" {
  description = "returns a string"
  value       = panos_panorama_template_stack.this.id
}

output "this" {
  value = panos_panorama_template_stack.this
}
```

[top](#index)