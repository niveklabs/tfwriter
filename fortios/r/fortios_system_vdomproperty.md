# fortios_system_vdomproperty

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
module "fortios_system_vdomproperty" {
  source = "./modules/fortios/r/fortios_system_vdomproperty"

  # custom_service - (optional) is a type of string
  custom_service = null
  # description - (optional) is a type of string
  description = null
  # dialup_tunnel - (optional) is a type of string
  dialup_tunnel = null
  # firewall_address - (optional) is a type of string
  firewall_address = null
  # firewall_addrgrp - (optional) is a type of string
  firewall_addrgrp = null
  # firewall_policy - (optional) is a type of string
  firewall_policy = null
  # ipsec_phase1 - (optional) is a type of string
  ipsec_phase1 = null
  # ipsec_phase1_interface - (optional) is a type of string
  ipsec_phase1_interface = null
  # ipsec_phase2 - (optional) is a type of string
  ipsec_phase2 = null
  # ipsec_phase2_interface - (optional) is a type of string
  ipsec_phase2_interface = null
  # log_disk_quota - (optional) is a type of string
  log_disk_quota = null
  # name - (optional) is a type of string
  name = null
  # onetime_schedule - (optional) is a type of string
  onetime_schedule = null
  # proxy - (optional) is a type of string
  proxy = null
  # recurring_schedule - (optional) is a type of string
  recurring_schedule = null
  # service_group - (optional) is a type of string
  service_group = null
  # session - (optional) is a type of string
  session = null
  # snmp_index - (optional) is a type of number
  snmp_index = null
  # sslvpn - (optional) is a type of string
  sslvpn = null
  # user - (optional) is a type of string
  user = null
  # user_group - (optional) is a type of string
  user_group = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dialup_tunnel" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_addrgrp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_phase1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_phase1_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_phase2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_phase2_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_disk_quota" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "onetime_schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recurring_schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snmp_index" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sslvpn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_group" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdomproperty" "this" {
  # custom_service - (optional) is a type of string
  custom_service = var.custom_service
  # description - (optional) is a type of string
  description = var.description
  # dialup_tunnel - (optional) is a type of string
  dialup_tunnel = var.dialup_tunnel
  # firewall_address - (optional) is a type of string
  firewall_address = var.firewall_address
  # firewall_addrgrp - (optional) is a type of string
  firewall_addrgrp = var.firewall_addrgrp
  # firewall_policy - (optional) is a type of string
  firewall_policy = var.firewall_policy
  # ipsec_phase1 - (optional) is a type of string
  ipsec_phase1 = var.ipsec_phase1
  # ipsec_phase1_interface - (optional) is a type of string
  ipsec_phase1_interface = var.ipsec_phase1_interface
  # ipsec_phase2 - (optional) is a type of string
  ipsec_phase2 = var.ipsec_phase2
  # ipsec_phase2_interface - (optional) is a type of string
  ipsec_phase2_interface = var.ipsec_phase2_interface
  # log_disk_quota - (optional) is a type of string
  log_disk_quota = var.log_disk_quota
  # name - (optional) is a type of string
  name = var.name
  # onetime_schedule - (optional) is a type of string
  onetime_schedule = var.onetime_schedule
  # proxy - (optional) is a type of string
  proxy = var.proxy
  # recurring_schedule - (optional) is a type of string
  recurring_schedule = var.recurring_schedule
  # service_group - (optional) is a type of string
  service_group = var.service_group
  # session - (optional) is a type of string
  session = var.session
  # snmp_index - (optional) is a type of number
  snmp_index = var.snmp_index
  # sslvpn - (optional) is a type of string
  sslvpn = var.sslvpn
  # user - (optional) is a type of string
  user = var.user
  # user_group - (optional) is a type of string
  user_group = var.user_group
}
```

[top](#index)

### Outputs

```terraform
output "custom_service" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.custom_service
}

output "description" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.description
}

output "dialup_tunnel" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.dialup_tunnel
}

output "firewall_address" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.firewall_address
}

output "firewall_addrgrp" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.firewall_addrgrp
}

output "firewall_policy" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.firewall_policy
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.id
}

output "ipsec_phase1" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.ipsec_phase1
}

output "ipsec_phase1_interface" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.ipsec_phase1_interface
}

output "ipsec_phase2" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.ipsec_phase2
}

output "ipsec_phase2_interface" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.ipsec_phase2_interface
}

output "log_disk_quota" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.log_disk_quota
}

output "name" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.name
}

output "onetime_schedule" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.onetime_schedule
}

output "proxy" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.proxy
}

output "recurring_schedule" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.recurring_schedule
}

output "service_group" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.service_group
}

output "session" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.session
}

output "snmp_index" {
  description = "returns a number"
  value       = fortios_system_vdomproperty.this.snmp_index
}

output "sslvpn" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.sslvpn
}

output "user" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.user
}

output "user_group" {
  description = "returns a string"
  value       = fortios_system_vdomproperty.this.user_group
}

output "this" {
  value = fortios_system_vdomproperty.this
}
```

[top](#index)