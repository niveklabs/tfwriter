# fortios_authentication_setting

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
module "fortios_authentication_setting" {
  source = "./modules/fortios/r/fortios_authentication_setting"

  # active_auth_scheme - (optional) is a type of string
  active_auth_scheme = null
  # auth_https - (optional) is a type of string
  auth_https = null
  # captive_portal - (optional) is a type of string
  captive_portal = null
  # captive_portal6 - (optional) is a type of string
  captive_portal6 = null
  # captive_portal_ip - (optional) is a type of string
  captive_portal_ip = null
  # captive_portal_ip6 - (optional) is a type of string
  captive_portal_ip6 = null
  # captive_portal_port - (optional) is a type of number
  captive_portal_port = null
  # captive_portal_ssl_port - (optional) is a type of number
  captive_portal_ssl_port = null
  # captive_portal_type - (optional) is a type of string
  captive_portal_type = null
  # sso_auth_scheme - (optional) is a type of string
  sso_auth_scheme = null
}
```

[top](#index)

### Variables

```terraform
variable "active_auth_scheme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_https" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "captive_portal_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "captive_portal_ssl_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "captive_portal_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_auth_scheme" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_authentication_setting" "this" {
  # active_auth_scheme - (optional) is a type of string
  active_auth_scheme = var.active_auth_scheme
  # auth_https - (optional) is a type of string
  auth_https = var.auth_https
  # captive_portal - (optional) is a type of string
  captive_portal = var.captive_portal
  # captive_portal6 - (optional) is a type of string
  captive_portal6 = var.captive_portal6
  # captive_portal_ip - (optional) is a type of string
  captive_portal_ip = var.captive_portal_ip
  # captive_portal_ip6 - (optional) is a type of string
  captive_portal_ip6 = var.captive_portal_ip6
  # captive_portal_port - (optional) is a type of number
  captive_portal_port = var.captive_portal_port
  # captive_portal_ssl_port - (optional) is a type of number
  captive_portal_ssl_port = var.captive_portal_ssl_port
  # captive_portal_type - (optional) is a type of string
  captive_portal_type = var.captive_portal_type
  # sso_auth_scheme - (optional) is a type of string
  sso_auth_scheme = var.sso_auth_scheme
}
```

[top](#index)

### Outputs

```terraform
output "active_auth_scheme" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.active_auth_scheme
}

output "auth_https" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.auth_https
}

output "captive_portal" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.captive_portal
}

output "captive_portal6" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.captive_portal6
}

output "captive_portal_ip" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.captive_portal_ip
}

output "captive_portal_ip6" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.captive_portal_ip6
}

output "captive_portal_port" {
  description = "returns a number"
  value       = fortios_authentication_setting.this.captive_portal_port
}

output "captive_portal_ssl_port" {
  description = "returns a number"
  value       = fortios_authentication_setting.this.captive_portal_ssl_port
}

output "captive_portal_type" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.captive_portal_type
}

output "id" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.id
}

output "sso_auth_scheme" {
  description = "returns a string"
  value       = fortios_authentication_setting.this.sso_auth_scheme
}

output "this" {
  value = fortios_authentication_setting.this
}
```

[top](#index)