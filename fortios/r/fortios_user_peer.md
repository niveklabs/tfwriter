# fortios_user_peer

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
module "fortios_user_peer" {
  source = "./modules/fortios/r/fortios_user_peer"

  # ca - (optional) is a type of string
  ca = null
  # cn - (optional) is a type of string
  cn = null
  # cn_type - (optional) is a type of string
  cn_type = null
  # ldap_mode - (optional) is a type of string
  ldap_mode = null
  # ldap_password - (optional) is a type of string
  ldap_password = null
  # ldap_server - (optional) is a type of string
  ldap_server = null
  # ldap_username - (optional) is a type of string
  ldap_username = null
  # mandatory_ca_verify - (optional) is a type of string
  mandatory_ca_verify = null
  # name - (optional) is a type of string
  name = null
  # ocsp_override_server - (optional) is a type of string
  ocsp_override_server = null
  # passwd - (optional) is a type of string
  passwd = null
  # subject - (optional) is a type of string
  subject = null
  # two_factor - (optional) is a type of string
  two_factor = null
}
```

[top](#index)

### Variables

```terraform
variable "ca" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cn_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mandatory_ca_verify" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocsp_override_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "passwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_peer" "this" {
  ca                   = var.ca
  cn                   = var.cn
  cn_type              = var.cn_type
  ldap_mode            = var.ldap_mode
  ldap_password        = var.ldap_password
  ldap_server          = var.ldap_server
  ldap_username        = var.ldap_username
  mandatory_ca_verify  = var.mandatory_ca_verify
  name                 = var.name
  ocsp_override_server = var.ocsp_override_server
  passwd               = var.passwd
  subject              = var.subject
  two_factor           = var.two_factor
}
```

[top](#index)

### Outputs

```terraform
output "ca" {
  description = "returns a string"
  value       = fortios_user_peer.this.ca
}

output "cn" {
  description = "returns a string"
  value       = fortios_user_peer.this.cn
}

output "cn_type" {
  description = "returns a string"
  value       = fortios_user_peer.this.cn_type
}

output "id" {
  description = "returns a string"
  value       = fortios_user_peer.this.id
}

output "ldap_mode" {
  description = "returns a string"
  value       = fortios_user_peer.this.ldap_mode
}

output "ldap_server" {
  description = "returns a string"
  value       = fortios_user_peer.this.ldap_server
}

output "ldap_username" {
  description = "returns a string"
  value       = fortios_user_peer.this.ldap_username
}

output "mandatory_ca_verify" {
  description = "returns a string"
  value       = fortios_user_peer.this.mandatory_ca_verify
}

output "name" {
  description = "returns a string"
  value       = fortios_user_peer.this.name
}

output "ocsp_override_server" {
  description = "returns a string"
  value       = fortios_user_peer.this.ocsp_override_server
}

output "subject" {
  description = "returns a string"
  value       = fortios_user_peer.this.subject
}

output "two_factor" {
  description = "returns a string"
  value       = fortios_user_peer.this.two_factor
}

output "this" {
  value = fortios_user_peer.this
}
```

[top](#index)