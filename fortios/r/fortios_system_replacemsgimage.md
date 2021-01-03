# fortios_system_replacemsgimage

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_replacemsgimage" {
  source = "./modules/fortios/r/fortios_system_replacemsgimage"

  # image_base64 - (optional) is a type of string
  image_base64 = null
  # image_type - (optional) is a type of string
  image_type = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "image_base64" {
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
```

[top](#index)

### Resource

```terraform
resource "fortios_system_replacemsgimage" "this" {
  image_base64 = var.image_base64
  image_type   = var.image_type
  name         = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_replacemsgimage.this.id
}

output "image_type" {
  description = "returns a string"
  value       = fortios_system_replacemsgimage.this.image_type
}

output "name" {
  description = "returns a string"
  value       = fortios_system_replacemsgimage.this.name
}

output "this" {
  value = fortios_system_replacemsgimage.this
}
```

[top](#index)