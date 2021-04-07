# fortios_system_fm

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
module "fortios_system_fm" {
  source = "./modules/fortios/r/fortios_system_fm"

  # auto_backup - (optional) is a type of string
  auto_backup = null
  # fosid - (optional) is a type of string
  fosid = null
  # ip - (optional) is a type of string
  ip = null
  # ipsec - (optional) is a type of string
  ipsec = null
  # scheduled_config_restore - (optional) is a type of string
  scheduled_config_restore = null
  # status - (optional) is a type of string
  status = null
  # vdom - (optional) is a type of string
  vdom = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_backup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduled_config_restore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
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
resource "fortios_system_fm" "this" {
  # auto_backup - (optional) is a type of string
  auto_backup = var.auto_backup
  # fosid - (optional) is a type of string
  fosid = var.fosid
  # ip - (optional) is a type of string
  ip = var.ip
  # ipsec - (optional) is a type of string
  ipsec = var.ipsec
  # scheduled_config_restore - (optional) is a type of string
  scheduled_config_restore = var.scheduled_config_restore
  # status - (optional) is a type of string
  status = var.status
  # vdom - (optional) is a type of string
  vdom = var.vdom
}
```

[top](#index)

### Outputs

```terraform
output "auto_backup" {
  description = "returns a string"
  value       = fortios_system_fm.this.auto_backup
}

output "fosid" {
  description = "returns a string"
  value       = fortios_system_fm.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_fm.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_system_fm.this.ip
}

output "ipsec" {
  description = "returns a string"
  value       = fortios_system_fm.this.ipsec
}

output "scheduled_config_restore" {
  description = "returns a string"
  value       = fortios_system_fm.this.scheduled_config_restore
}

output "status" {
  description = "returns a string"
  value       = fortios_system_fm.this.status
}

output "vdom" {
  description = "returns a string"
  value       = fortios_system_fm.this.vdom
}

output "this" {
  value = fortios_system_fm.this
}
```

[top](#index)