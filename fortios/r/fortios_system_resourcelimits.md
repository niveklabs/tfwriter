# fortios_system_resourcelimits

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
module "fortios_system_resourcelimits" {
  source = "./modules/fortios/r/fortios_system_resourcelimits"

  # custom_service - (optional) is a type of number
  custom_service = null
  # dialup_tunnel - (optional) is a type of number
  dialup_tunnel = null
  # firewall_address - (optional) is a type of number
  firewall_address = null
  # firewall_addrgrp - (optional) is a type of number
  firewall_addrgrp = null
  # firewall_policy - (optional) is a type of number
  firewall_policy = null
  # ipsec_phase1 - (optional) is a type of number
  ipsec_phase1 = null
  # ipsec_phase1_interface - (optional) is a type of number
  ipsec_phase1_interface = null
  # ipsec_phase2 - (optional) is a type of number
  ipsec_phase2 = null
  # ipsec_phase2_interface - (optional) is a type of number
  ipsec_phase2_interface = null
  # log_disk_quota - (optional) is a type of number
  log_disk_quota = null
  # onetime_schedule - (optional) is a type of number
  onetime_schedule = null
  # proxy - (optional) is a type of number
  proxy = null
  # recurring_schedule - (optional) is a type of number
  recurring_schedule = null
  # service_group - (optional) is a type of number
  service_group = null
  # session - (optional) is a type of number
  session = null
  # sslvpn - (optional) is a type of number
  sslvpn = null
  # user - (optional) is a type of number
  user = null
  # user_group - (optional) is a type of number
  user_group = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_service" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dialup_tunnel" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "firewall_address" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "firewall_addrgrp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "firewall_policy" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipsec_phase1" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipsec_phase1_interface" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipsec_phase2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipsec_phase2_interface" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_disk_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "onetime_schedule" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "recurring_schedule" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sslvpn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_group" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_resourcelimits" "this" {
  custom_service         = var.custom_service
  dialup_tunnel          = var.dialup_tunnel
  firewall_address       = var.firewall_address
  firewall_addrgrp       = var.firewall_addrgrp
  firewall_policy        = var.firewall_policy
  ipsec_phase1           = var.ipsec_phase1
  ipsec_phase1_interface = var.ipsec_phase1_interface
  ipsec_phase2           = var.ipsec_phase2
  ipsec_phase2_interface = var.ipsec_phase2_interface
  log_disk_quota         = var.log_disk_quota
  onetime_schedule       = var.onetime_schedule
  proxy                  = var.proxy
  recurring_schedule     = var.recurring_schedule
  service_group          = var.service_group
  session                = var.session
  sslvpn                 = var.sslvpn
  user                   = var.user
  user_group             = var.user_group
}
```

[top](#index)

### Outputs

```terraform
output "custom_service" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.custom_service
}

output "dialup_tunnel" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.dialup_tunnel
}

output "firewall_address" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.firewall_address
}

output "firewall_addrgrp" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.firewall_addrgrp
}

output "firewall_policy" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.firewall_policy
}

output "id" {
  description = "returns a string"
  value       = fortios_system_resourcelimits.this.id
}

output "ipsec_phase1" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.ipsec_phase1
}

output "ipsec_phase1_interface" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.ipsec_phase1_interface
}

output "ipsec_phase2" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.ipsec_phase2
}

output "ipsec_phase2_interface" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.ipsec_phase2_interface
}

output "log_disk_quota" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.log_disk_quota
}

output "onetime_schedule" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.onetime_schedule
}

output "proxy" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.proxy
}

output "recurring_schedule" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.recurring_schedule
}

output "service_group" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.service_group
}

output "session" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.session
}

output "sslvpn" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.sslvpn
}

output "user" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.user
}

output "user_group" {
  description = "returns a number"
  value       = fortios_system_resourcelimits.this.user_group
}

output "this" {
  value = fortios_system_resourcelimits.this
}
```

[top](#index)