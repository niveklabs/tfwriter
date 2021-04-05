# panos_panorama_zone_entry

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
module "panos_panorama_zone_entry" {
  source = "./modules/panos/r/panos_panorama_zone_entry"

  # interface - (required) is a type of string
  interface = null
  # mode - (optional) is a type of string
  mode = null
  # template - (required) is a type of string
  template = null
  # vsys - (optional) is a type of string
  vsys = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_zone_entry" "this" {
  interface = var.interface
  mode      = var.mode
  template  = var.template
  vsys      = var.vsys
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_zone_entry.this.id
}

output "this" {
  value = panos_panorama_zone_entry.this
}
```

[top](#index)