# panos_panorama_template_entry

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_template_entry" {
  source = "./modules/panos/r/panos_panorama_template_entry"

  # serial - (required) is a type of string
  serial = null
  # template - (required) is a type of string
  template = null
  # vsys_list - (optional) is a type of set of string
  vsys_list = []
}
```

[top](#index)

### Variables

```terraform
variable "serial" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "vsys_list" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_template_entry" "this" {
  serial    = var.serial
  template  = var.template
  vsys_list = var.vsys_list
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_template_entry.this.id
}

output "this" {
  value = panos_panorama_template_entry.this
}
```

[top](#index)