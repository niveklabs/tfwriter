# fortios_user_local

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
module "fortios_user_local" {
  source = "./modules/fortios/r/fortios_user_local"

  # auth_concurrent_override - (optional) is a type of string
  auth_concurrent_override = null
  # auth_concurrent_value - (optional) is a type of number
  auth_concurrent_value = null
  # authtimeout - (optional) is a type of number
  authtimeout = null
  # email_to - (optional) is a type of string
  email_to = null
  # fortitoken - (optional) is a type of string
  fortitoken = null
  # fosid - (optional) is a type of number
  fosid = null
  # ldap_server - (optional) is a type of string
  ldap_server = null
  # name - (optional) is a type of string
  name = null
  # passwd - (optional) is a type of string
  passwd = null
  # passwd_policy - (optional) is a type of string
  passwd_policy = null
  # passwd_time - (optional) is a type of string
  passwd_time = null
  # ppk_identity - (optional) is a type of string
  ppk_identity = null
  # ppk_secret - (optional) is a type of string
  ppk_secret = null
  # radius_server - (optional) is a type of string
  radius_server = null
  # sms_custom_server - (optional) is a type of string
  sms_custom_server = null
  # sms_phone - (optional) is a type of string
  sms_phone = null
  # sms_server - (optional) is a type of string
  sms_server = null
  # status - (required) is a type of string
  status = null
  # tacacs_server - (optional) is a type of string
  tacacs_server = null
  # two_factor - (optional) is a type of string
  two_factor = null
  # two_factor_authentication - (optional) is a type of string
  two_factor_authentication = null
  # two_factor_notification - (optional) is a type of string
  two_factor_notification = null
  # type - (required) is a type of string
  type = null
  # username_case_insensitivity - (optional) is a type of string
  username_case_insensitivity = null
  # username_case_sensitivity - (optional) is a type of string
  username_case_sensitivity = null
  # workstation - (optional) is a type of string
  workstation = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_concurrent_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_concurrent_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authtimeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "email_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortitoken" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ldap_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passwd_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passwd_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppk_identity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppk_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_custom_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "tacacs_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor_authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor_notification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "username_case_insensitivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username_case_sensitivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workstation" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_local" "this" {
  # auth_concurrent_override - (optional) is a type of string
  auth_concurrent_override = var.auth_concurrent_override
  # auth_concurrent_value - (optional) is a type of number
  auth_concurrent_value = var.auth_concurrent_value
  # authtimeout - (optional) is a type of number
  authtimeout = var.authtimeout
  # email_to - (optional) is a type of string
  email_to = var.email_to
  # fortitoken - (optional) is a type of string
  fortitoken = var.fortitoken
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # ldap_server - (optional) is a type of string
  ldap_server = var.ldap_server
  # name - (optional) is a type of string
  name = var.name
  # passwd - (optional) is a type of string
  passwd = var.passwd
  # passwd_policy - (optional) is a type of string
  passwd_policy = var.passwd_policy
  # passwd_time - (optional) is a type of string
  passwd_time = var.passwd_time
  # ppk_identity - (optional) is a type of string
  ppk_identity = var.ppk_identity
  # ppk_secret - (optional) is a type of string
  ppk_secret = var.ppk_secret
  # radius_server - (optional) is a type of string
  radius_server = var.radius_server
  # sms_custom_server - (optional) is a type of string
  sms_custom_server = var.sms_custom_server
  # sms_phone - (optional) is a type of string
  sms_phone = var.sms_phone
  # sms_server - (optional) is a type of string
  sms_server = var.sms_server
  # status - (required) is a type of string
  status = var.status
  # tacacs_server - (optional) is a type of string
  tacacs_server = var.tacacs_server
  # two_factor - (optional) is a type of string
  two_factor = var.two_factor
  # two_factor_authentication - (optional) is a type of string
  two_factor_authentication = var.two_factor_authentication
  # two_factor_notification - (optional) is a type of string
  two_factor_notification = var.two_factor_notification
  # type - (required) is a type of string
  type = var.type
  # username_case_insensitivity - (optional) is a type of string
  username_case_insensitivity = var.username_case_insensitivity
  # username_case_sensitivity - (optional) is a type of string
  username_case_sensitivity = var.username_case_sensitivity
  # workstation - (optional) is a type of string
  workstation = var.workstation
}
```

[top](#index)

### Outputs

```terraform
output "auth_concurrent_override" {
  description = "returns a string"
  value       = fortios_user_local.this.auth_concurrent_override
}

output "auth_concurrent_value" {
  description = "returns a number"
  value       = fortios_user_local.this.auth_concurrent_value
}

output "authtimeout" {
  description = "returns a number"
  value       = fortios_user_local.this.authtimeout
}

output "email_to" {
  description = "returns a string"
  value       = fortios_user_local.this.email_to
}

output "fortitoken" {
  description = "returns a string"
  value       = fortios_user_local.this.fortitoken
}

output "fosid" {
  description = "returns a number"
  value       = fortios_user_local.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_user_local.this.id
}

output "ldap_server" {
  description = "returns a string"
  value       = fortios_user_local.this.ldap_server
}

output "name" {
  description = "returns a string"
  value       = fortios_user_local.this.name
}

output "passwd_policy" {
  description = "returns a string"
  value       = fortios_user_local.this.passwd_policy
}

output "passwd_time" {
  description = "returns a string"
  value       = fortios_user_local.this.passwd_time
}

output "ppk_identity" {
  description = "returns a string"
  value       = fortios_user_local.this.ppk_identity
}

output "radius_server" {
  description = "returns a string"
  value       = fortios_user_local.this.radius_server
}

output "sms_custom_server" {
  description = "returns a string"
  value       = fortios_user_local.this.sms_custom_server
}

output "sms_phone" {
  description = "returns a string"
  value       = fortios_user_local.this.sms_phone
}

output "sms_server" {
  description = "returns a string"
  value       = fortios_user_local.this.sms_server
}

output "tacacs_server" {
  description = "returns a string"
  value       = fortios_user_local.this.tacacs_server
}

output "two_factor" {
  description = "returns a string"
  value       = fortios_user_local.this.two_factor
}

output "two_factor_authentication" {
  description = "returns a string"
  value       = fortios_user_local.this.two_factor_authentication
}

output "two_factor_notification" {
  description = "returns a string"
  value       = fortios_user_local.this.two_factor_notification
}

output "username_case_insensitivity" {
  description = "returns a string"
  value       = fortios_user_local.this.username_case_insensitivity
}

output "username_case_sensitivity" {
  description = "returns a string"
  value       = fortios_user_local.this.username_case_sensitivity
}

output "workstation" {
  description = "returns a string"
  value       = fortios_user_local.this.workstation
}

output "this" {
  value = fortios_user_local.this
}
```

[top](#index)