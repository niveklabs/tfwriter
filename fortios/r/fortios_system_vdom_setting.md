# fortios_system_vdom_setting

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
module "fortios_system_vdom_setting" {
  source = "./modules/fortios/r/fortios_system_vdom_setting"

  # name - (required) is a type of string
  name = null
  # short_name - (optional) is a type of string
  short_name = null
  # temporary - (optional) is a type of string
  temporary = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "short_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "temporary" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdom_setting" "this" {
  name       = var.name
  short_name = var.short_name
  temporary  = var.temporary
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_vdom_setting.this.id
}

output "short_name" {
  description = "returns a string"
  value       = fortios_system_vdom_setting.this.short_name
}

output "temporary" {
  description = "returns a string"
  value       = fortios_system_vdom_setting.this.temporary
}

output "this" {
  value = fortios_system_vdom_setting.this
}
```

[top](#index)