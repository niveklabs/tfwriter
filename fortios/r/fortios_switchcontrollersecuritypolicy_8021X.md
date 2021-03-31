# fortios_switchcontrollersecuritypolicy_8021X

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
module "fortios_switchcontrollersecuritypolicy_8021X" {
  source = "./modules/fortios/r/fortios_switchcontrollersecuritypolicy_8021X"

  # auth_fail_vlan - (optional) is a type of string
  auth_fail_vlan = null
  # auth_fail_vlan_id - (optional) is a type of string
  auth_fail_vlan_id = null
  # auth_fail_vlanid - (optional) is a type of number
  auth_fail_vlanid = null
  # authserver_timeout_period - (optional) is a type of number
  authserver_timeout_period = null
  # authserver_timeout_vlan - (optional) is a type of string
  authserver_timeout_vlan = null
  # authserver_timeout_vlanid - (optional) is a type of string
  authserver_timeout_vlanid = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # eap_auto_untagged_vlans - (optional) is a type of string
  eap_auto_untagged_vlans = null
  # eap_passthru - (optional) is a type of string
  eap_passthru = null
  # framevid_apply - (optional) is a type of string
  framevid_apply = null
  # guest_auth_delay - (optional) is a type of number
  guest_auth_delay = null
  # guest_vlan - (optional) is a type of string
  guest_vlan = null
  # guest_vlan_id - (optional) is a type of string
  guest_vlan_id = null
  # guest_vlanid - (optional) is a type of number
  guest_vlanid = null
  # mac_auth_bypass - (optional) is a type of string
  mac_auth_bypass = null
  # name - (optional) is a type of string
  name = null
  # open_auth - (optional) is a type of string
  open_auth = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # radius_timeout_overwrite - (optional) is a type of string
  radius_timeout_overwrite = null
  # security_mode - (optional) is a type of string
  security_mode = null

  user_group = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_fail_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_fail_vlan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_fail_vlanid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authserver_timeout_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authserver_timeout_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authserver_timeout_vlanid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap_auto_untagged_vlans" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap_passthru" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "framevid_apply" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_auth_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "guest_vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_vlan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_vlanid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac_auth_bypass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "open_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_timeout_overwrite" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollersecuritypolicy_8021X" "this" {
  auth_fail_vlan            = var.auth_fail_vlan
  auth_fail_vlan_id         = var.auth_fail_vlan_id
  auth_fail_vlanid          = var.auth_fail_vlanid
  authserver_timeout_period = var.authserver_timeout_period
  authserver_timeout_vlan   = var.authserver_timeout_vlan
  authserver_timeout_vlanid = var.authserver_timeout_vlanid
  dynamic_sort_subtable     = var.dynamic_sort_subtable
  eap_auto_untagged_vlans   = var.eap_auto_untagged_vlans
  eap_passthru              = var.eap_passthru
  framevid_apply            = var.framevid_apply
  guest_auth_delay          = var.guest_auth_delay
  guest_vlan                = var.guest_vlan
  guest_vlan_id             = var.guest_vlan_id
  guest_vlanid              = var.guest_vlanid
  mac_auth_bypass           = var.mac_auth_bypass
  name                      = var.name
  open_auth                 = var.open_auth
  policy_type               = var.policy_type
  radius_timeout_overwrite  = var.radius_timeout_overwrite
  security_mode             = var.security_mode

  dynamic "user_group" {
    for_each = var.user_group
    content {
      name = user_group.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_fail_vlan" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.auth_fail_vlan
}

output "auth_fail_vlan_id" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.auth_fail_vlan_id
}

output "auth_fail_vlanid" {
  description = "returns a number"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.auth_fail_vlanid
}

output "authserver_timeout_period" {
  description = "returns a number"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.authserver_timeout_period
}

output "authserver_timeout_vlan" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.authserver_timeout_vlan
}

output "authserver_timeout_vlanid" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.authserver_timeout_vlanid
}

output "eap_auto_untagged_vlans" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.eap_auto_untagged_vlans
}

output "eap_passthru" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.eap_passthru
}

output "framevid_apply" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.framevid_apply
}

output "guest_auth_delay" {
  description = "returns a number"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.guest_auth_delay
}

output "guest_vlan" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.guest_vlan
}

output "guest_vlan_id" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.guest_vlan_id
}

output "guest_vlanid" {
  description = "returns a number"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.guest_vlanid
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.id
}

output "mac_auth_bypass" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.mac_auth_bypass
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.name
}

output "open_auth" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.open_auth
}

output "policy_type" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.policy_type
}

output "radius_timeout_overwrite" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.radius_timeout_overwrite
}

output "security_mode" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_8021X.this.security_mode
}

output "this" {
  value = fortios_switchcontrollersecuritypolicy_8021X.this
}
```

[top](#index)