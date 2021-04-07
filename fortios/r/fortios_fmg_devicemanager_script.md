# fortios_fmg_devicemanager_script

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
module "fortios_fmg_devicemanager_script" {
  source = "./modules/fortios/r/fortios_fmg_devicemanager_script"

  # adom - (optional) is a type of string
  adom = null
  # content - (required) is a type of string
  content = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # target - (optional) is a type of string
  target = null
}
```

[top](#index)

### Variables

```terraform
variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_devicemanager_script" "this" {
  # adom - (optional) is a type of string
  adom = var.adom
  # content - (required) is a type of string
  content = var.content
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # target - (optional) is a type of string
  target = var.target
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_devicemanager_script.this.id
}

output "this" {
  value = fortios_fmg_devicemanager_script.this
}
```

[top](#index)