# fortios_switchcontroller_nacsettings

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
module "fortios_switchcontroller_nacsettings" {
  source = "./modules/fortios/r/fortios_switchcontroller_nacsettings"

  # auto_auth - (optional) is a type of string
  auto_auth = null
  # bounce_nac_port - (optional) is a type of string
  bounce_nac_port = null
  # inactive_timer - (optional) is a type of number
  inactive_timer = null
  # link_down_flush - (optional) is a type of string
  link_down_flush = null
  # mode - (optional) is a type of string
  mode = null
  # name - (optional) is a type of string
  name = null
  # onboarding_vlan - (optional) is a type of string
  onboarding_vlan = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bounce_nac_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inactive_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "link_down_flush" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "onboarding_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_nacsettings" "this" {
  # auto_auth - (optional) is a type of string
  auto_auth = var.auto_auth
  # bounce_nac_port - (optional) is a type of string
  bounce_nac_port = var.bounce_nac_port
  # inactive_timer - (optional) is a type of number
  inactive_timer = var.inactive_timer
  # link_down_flush - (optional) is a type of string
  link_down_flush = var.link_down_flush
  # mode - (optional) is a type of string
  mode = var.mode
  # name - (optional) is a type of string
  name = var.name
  # onboarding_vlan - (optional) is a type of string
  onboarding_vlan = var.onboarding_vlan
}
```

[top](#index)

### Outputs

```terraform
output "auto_auth" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.auto_auth
}

output "bounce_nac_port" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.bounce_nac_port
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.id
}

output "inactive_timer" {
  description = "returns a number"
  value       = fortios_switchcontroller_nacsettings.this.inactive_timer
}

output "link_down_flush" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.link_down_flush
}

output "mode" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.mode
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.name
}

output "onboarding_vlan" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacsettings.this.onboarding_vlan
}

output "this" {
  value = fortios_switchcontroller_nacsettings.this
}
```

[top](#index)