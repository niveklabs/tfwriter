# fortios_fmg_devicemanager_install_policypackage

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
module "fortios_fmg_devicemanager_install_policypackage" {
  source = "./modules/fortios/r/fortios_fmg_devicemanager_install_policypackage"

  # adom - (optional) is a type of string
  adom = null
  # package_name - (required) is a type of string
  package_name = null
  # timeout - (optional) is a type of number
  timeout = null
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

variable "package_name" {
  description = "(required)"
  type        = string
}

variable "timeout" {
  description = "(optional) - Timeout for installing the package to the target, default: 3 minutes"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_devicemanager_install_policypackage" "this" {
  # adom - (optional) is a type of string
  adom = var.adom
  # package_name - (required) is a type of string
  package_name = var.package_name
  # timeout - (optional) is a type of number
  timeout = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_devicemanager_install_policypackage.this.id
}

output "this" {
  value = fortios_fmg_devicemanager_install_policypackage.this
}
```

[top](#index)