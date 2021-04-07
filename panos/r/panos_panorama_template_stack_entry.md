# panos_panorama_template_stack_entry

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
module "panos_panorama_template_stack_entry" {
  source = "./modules/panos/r/panos_panorama_template_stack_entry"

  # device - (required) is a type of string
  device = null
  # template_stack - (required) is a type of string
  template_stack = null
}
```

[top](#index)

### Variables

```terraform
variable "device" {
  description = "(required)"
  type        = string
}

variable "template_stack" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_template_stack_entry" "this" {
  # device - (required) is a type of string
  device = var.device
  # template_stack - (required) is a type of string
  template_stack = var.template_stack
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_template_stack_entry.this.id
}

output "this" {
  value = panos_panorama_template_stack_entry.this
}
```

[top](#index)