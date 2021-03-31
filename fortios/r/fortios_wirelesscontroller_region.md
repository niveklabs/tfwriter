# fortios_wirelesscontroller_region

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontroller_region" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_region"

  # comments - (optional) is a type of string
  comments = null
  # grayscale - (optional) is a type of string
  grayscale = null
  # image_type - (optional) is a type of string
  image_type = null
  # name - (optional) is a type of string
  name = null
  # opacity - (optional) is a type of number
  opacity = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "grayscale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opacity" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_region" "this" {
  comments   = var.comments
  grayscale  = var.grayscale
  image_type = var.image_type
  name       = var.name
  opacity    = var.opacity
}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_region.this.comments
}

output "grayscale" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_region.this.grayscale
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_region.this.id
}

output "image_type" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_region.this.image_type
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_region.this.name
}

output "opacity" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_region.this.opacity
}

output "this" {
  value = fortios_wirelesscontroller_region.this
}
```

[top](#index)