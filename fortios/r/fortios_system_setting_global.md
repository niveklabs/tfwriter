# fortios_system_setting_global

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
module "fortios_system_setting_global" {
  source = "./modules/fortios/r/fortios_system_setting_global"

  # admin_scp - (optional) is a type of string
  admin_scp = null
  # admin_sport - (optional) is a type of string
  admin_sport = null
  # admin_ssh_port - (optional) is a type of string
  admin_ssh_port = null
  # admintimeout - (optional) is a type of string
  admintimeout = null
  # hostname - (required) is a type of string
  hostname = null
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_scp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_sport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_ssh_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admintimeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_setting_global" "this" {
  # admin_scp - (optional) is a type of string
  admin_scp = var.admin_scp
  # admin_sport - (optional) is a type of string
  admin_sport = var.admin_sport
  # admin_ssh_port - (optional) is a type of string
  admin_ssh_port = var.admin_ssh_port
  # admintimeout - (optional) is a type of string
  admintimeout = var.admintimeout
  # hostname - (required) is a type of string
  hostname = var.hostname
  # timezone - (optional) is a type of string
  timezone = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "admin_scp" {
  description = "returns a string"
  value       = fortios_system_setting_global.this.admin_scp
}

output "admin_sport" {
  description = "returns a string"
  value       = fortios_system_setting_global.this.admin_sport
}

output "admin_ssh_port" {
  description = "returns a string"
  value       = fortios_system_setting_global.this.admin_ssh_port
}

output "admintimeout" {
  description = "returns a string"
  value       = fortios_system_setting_global.this.admintimeout
}

output "id" {
  description = "returns a string"
  value       = fortios_system_setting_global.this.id
}

output "timezone" {
  description = "returns a string"
  value       = fortios_system_setting_global.this.timezone
}

output "this" {
  value = fortios_system_setting_global.this
}
```

[top](#index)