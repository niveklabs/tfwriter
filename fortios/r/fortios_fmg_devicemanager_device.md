# fortios_fmg_devicemanager_device

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
module "fortios_fmg_devicemanager_device" {
  source = "./modules/fortios/r/fortios_fmg_devicemanager_device"

  # adom - (optional) is a type of string
  adom = null
  # device_name - (required) is a type of string
  device_name = null
  # ipaddr - (required) is a type of string
  ipaddr = null
  # password - (optional) is a type of string
  password = null
  # userid - (required) is a type of string
  userid = null
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

variable "device_name" {
  description = "(required)"
  type        = string
}

variable "ipaddr" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "userid" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_devicemanager_device" "this" {
  adom        = var.adom
  device_name = var.device_name
  ipaddr      = var.ipaddr
  password    = var.password
  userid      = var.userid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_devicemanager_device.this.id
}

output "this" {
  value = fortios_fmg_devicemanager_device.this
}
```

[top](#index)