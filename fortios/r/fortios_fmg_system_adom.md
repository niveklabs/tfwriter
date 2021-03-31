# fortios_fmg_system_adom

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
module "fortios_fmg_system_adom" {
  source = "./modules/fortios/r/fortios_fmg_system_adom"

  # action_when_conflicts_occur_during_policy_check - (optional) is a type of string
  action_when_conflicts_occur_during_policy_check = null
  # auto_push_policy_packages_when_device_back_online - (optional) is a type of string
  auto_push_policy_packages_when_device_back_online = null
  # central_management_fortiap - (optional) is a type of bool
  central_management_fortiap = null
  # central_management_sdwan - (optional) is a type of bool
  central_management_sdwan = null
  # central_management_vpn - (optional) is a type of bool
  central_management_vpn = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # perform_policy_check_before_every_install - (optional) is a type of bool
  perform_policy_check_before_every_install = null
  # status - (optional) is a type of number
  status = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "action_when_conflicts_occur_during_policy_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_push_policy_packages_when_device_back_online" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "central_management_fortiap" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "central_management_sdwan" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "central_management_vpn" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "perform_policy_check_before_every_install" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_adom" "this" {
  action_when_conflicts_occur_during_policy_check   = var.action_when_conflicts_occur_during_policy_check
  auto_push_policy_packages_when_device_back_online = var.auto_push_policy_packages_when_device_back_online
  central_management_fortiap                        = var.central_management_fortiap
  central_management_sdwan                          = var.central_management_sdwan
  central_management_vpn                            = var.central_management_vpn
  mode                                              = var.mode
  name                                              = var.name
  perform_policy_check_before_every_install         = var.perform_policy_check_before_every_install
  status                                            = var.status
  type                                              = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_adom.this.id
}

output "this" {
  value = fortios_fmg_system_adom.this
}
```

[top](#index)