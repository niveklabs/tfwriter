# fortios_system_autoinstall

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
module "fortios_system_autoinstall" {
  source = "./modules/fortios/r/fortios_system_autoinstall"

  # auto_install_config - (optional) is a type of string
  auto_install_config = null
  # auto_install_image - (optional) is a type of string
  auto_install_image = null
  # default_config_file - (optional) is a type of string
  default_config_file = null
  # default_image_file - (optional) is a type of string
  default_image_file = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_install_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_install_image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_config_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_image_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_autoinstall" "this" {
  auto_install_config = var.auto_install_config
  auto_install_image  = var.auto_install_image
  default_config_file = var.default_config_file
  default_image_file  = var.default_image_file
}
```

[top](#index)

### Outputs

```terraform
output "auto_install_config" {
  description = "returns a string"
  value       = fortios_system_autoinstall.this.auto_install_config
}

output "auto_install_image" {
  description = "returns a string"
  value       = fortios_system_autoinstall.this.auto_install_image
}

output "default_config_file" {
  description = "returns a string"
  value       = fortios_system_autoinstall.this.default_config_file
}

output "default_image_file" {
  description = "returns a string"
  value       = fortios_system_autoinstall.this.default_image_file
}

output "id" {
  description = "returns a string"
  value       = fortios_system_autoinstall.this.id
}

output "this" {
  value = fortios_system_autoinstall.this
}
```

[top](#index)