# fortios_fmg_devicemanager_script_execute

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
module "fortios_fmg_devicemanager_script_execute" {
  source = "./modules/fortios/r/fortios_fmg_devicemanager_script_execute"

  # adom - (optional) is a type of string
  adom = null
  # package - (optional) is a type of string
  package = null
  # script_name - (required) is a type of string
  script_name = null
  # target_devname - (optional) is a type of string
  target_devname = null
  # timeout - (optional) is a type of number
  timeout = null
  # vdom - (optional) is a type of string
  vdom = null
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

variable "package" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script_name" {
  description = "(required)"
  type        = string
}

variable "target_devname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_devicemanager_script_execute" "this" {
  adom           = var.adom
  package        = var.package
  script_name    = var.script_name
  target_devname = var.target_devname
  timeout        = var.timeout
  vdom           = var.vdom
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_devicemanager_script_execute.this.id
}

output "this" {
  value = fortios_fmg_devicemanager_script_execute.this
}
```

[top](#index)