# panos_zone_entry

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
module "panos_zone_entry" {
  source = "./modules/panos/r/panos_zone_entry"

  # interface - (required) is a type of string
  interface = null
  # mode - (optional) is a type of string
  mode = null
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
resource "panos_zone_entry" "this" {
  # interface - (required) is a type of string
  interface = var.interface
  # mode - (optional) is a type of string
  mode = var.mode
  # vsys - (optional) is a type of string
  vsys = var.vsys
  # zone - (required) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_zone_entry.this.id
}

output "this" {
  value = panos_zone_entry.this
}
```

[top](#index)