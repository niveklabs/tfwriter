# fortios_system_customlanguage

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
module "fortios_system_customlanguage" {
  source = "./modules/fortios/r/fortios_system_customlanguage"

  # comments - (optional) is a type of string
  comments = null
  # filename - (required) is a type of string
  filename = null
  # name - (required) is a type of string
  name = null
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

variable "filename" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_customlanguage" "this" {
  comments = var.comments
  filename = var.filename
  name     = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_customlanguage.this.id
}

output "this" {
  value = fortios_system_customlanguage.this
}
```

[top](#index)