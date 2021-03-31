# fortios_fmg_devicemanager_install_device

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
module "fortios_fmg_devicemanager_install_device" {
  source = "./modules/fortios/r/fortios_fmg_devicemanager_install_device"

  # adom - (optional) is a type of string
  adom = null
  # target_devname - (required) is a type of string
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

variable "target_devname" {
  description = "(required)"
  type        = string
}

variable "timeout" {
  description = "(optional) - Timeout for installing the script to the target, default: 3 minutes"
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
resource "fortios_fmg_devicemanager_install_device" "this" {
  adom           = var.adom
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
  value       = fortios_fmg_devicemanager_install_device.this.id
}

output "this" {
  value = fortios_fmg_devicemanager_install_device.this
}
```

[top](#index)