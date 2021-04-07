# fortios_switchcontrollerinitialconfig_vlans

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
module "fortios_switchcontrollerinitialconfig_vlans" {
  source = "./modules/fortios/r/fortios_switchcontrollerinitialconfig_vlans"

  # default_vlan - (optional) is a type of string
  default_vlan = null
  # nac - (optional) is a type of string
  nac = null
  # quarantine - (optional) is a type of string
  quarantine = null
  # rspan - (optional) is a type of string
  rspan = null
  # video - (optional) is a type of string
  video = null
  # voice - (optional) is a type of string
  voice = null
}
```

[top](#index)

### Variables

```terraform
variable "default_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quarantine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rspan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "video" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voice" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerinitialconfig_vlans" "this" {
  # default_vlan - (optional) is a type of string
  default_vlan = var.default_vlan
  # nac - (optional) is a type of string
  nac = var.nac
  # quarantine - (optional) is a type of string
  quarantine = var.quarantine
  # rspan - (optional) is a type of string
  rspan = var.rspan
  # video - (optional) is a type of string
  video = var.video
  # voice - (optional) is a type of string
  voice = var.voice
}
```

[top](#index)

### Outputs

```terraform
output "default_vlan" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.default_vlan
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.id
}

output "nac" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.nac
}

output "quarantine" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.quarantine
}

output "rspan" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.rspan
}

output "video" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.video
}

output "voice" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_vlans.this.voice
}

output "this" {
  value = fortios_switchcontrollerinitialconfig_vlans.this
}
```

[top](#index)