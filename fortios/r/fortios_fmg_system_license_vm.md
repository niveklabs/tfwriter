# fortios_fmg_system_license_vm

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
module "fortios_fmg_system_license_vm" {
  source = "./modules/fortios/r/fortios_fmg_system_license_vm"

  # adom - (optional) is a type of string
  adom = null
  # file_content - (required) is a type of string
  file_content = null
  # target - (required) is a type of string
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

variable "file_content" {
  description = "(required)"
  type        = string
}

variable "target" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_license_vm" "this" {
  # adom - (optional) is a type of string
  adom = var.adom
  # file_content - (required) is a type of string
  file_content = var.file_content
  # target - (required) is a type of string
  target = var.target
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_license_vm.this.id
}

output "this" {
  value = fortios_fmg_system_license_vm.this
}
```

[top](#index)