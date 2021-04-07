# panos_panorama_template_variable

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
module "panos_panorama_template_variable" {
  source = "./modules/panos/r/panos_panorama_template_variable"

  # name - (required) is a type of string
  name = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # type - (optional) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_template_variable" "this" {
  # name - (required) is a type of string
  name = var.name
  # template - (optional) is a type of string
  template = var.template
  # template_stack - (optional) is a type of string
  template_stack = var.template_stack
  # type - (optional) is a type of string
  type = var.type
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_template_variable.this.id
}

output "this" {
  value = panos_panorama_template_variable.this
}
```

[top](#index)