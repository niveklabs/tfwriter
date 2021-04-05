# panos_layer2_subinterface

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
module "panos_layer2_subinterface" {
  source = "./modules/panos/r/panos_layer2_subinterface"

  # comment - (optional) is a type of string
  comment = null
  # interface_type - (optional) is a type of string
  interface_type = null
  # name - (required) is a type of string
  name = null
  # netflow_profile - (optional) is a type of string
  netflow_profile = null
  # parent_interface - (required) is a type of string
  parent_interface = null
  # parent_mode - (optional) is a type of string
  parent_mode = null
  # tag - (optional) is a type of number
  tag = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "netflow_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_interface" {
  description = "(required)"
  type        = string
}

variable "parent_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_layer2_subinterface" "this" {
  comment          = var.comment
  interface_type   = var.interface_type
  name             = var.name
  netflow_profile  = var.netflow_profile
  parent_interface = var.parent_interface
  parent_mode      = var.parent_mode
  tag              = var.tag
  vsys             = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_layer2_subinterface.this.id
}

output "this" {
  value = panos_layer2_subinterface.this
}
```

[top](#index)