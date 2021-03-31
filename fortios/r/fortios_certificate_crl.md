# fortios_certificate_crl

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
module "fortios_certificate_crl" {
  source = null

  # crl - (optional) is a type of string
  crl = null
  # http_url - (optional) is a type of string
  http_url = null
  # last_updated - (optional) is a type of number
  last_updated = null
  # ldap_password - (optional) is a type of string
  ldap_password = null
  # ldap_server - (optional) is a type of string
  ldap_server = null
  # ldap_username - (optional) is a type of string
  ldap_username = null
  # name - (required) is a type of string
  name = null
  # range - (optional) is a type of string
  range = null
  # scep_cert - (optional) is a type of string
  scep_cert = null
  # scep_url - (optional) is a type of string
  scep_url = null
  # source - (optional) is a type of string
  # source_ip - (optional) is a type of string
  source_ip = null
  # update_interval - (optional) is a type of number
  update_interval = null
  # update_vdom - (optional) is a type of string
  update_vdom = null
}
```

[top](#index)

### Variables

```terraform
variable "crl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_updated" {
  description = "(optional)"
  type        = number
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scep_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scep_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "update_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_certificate_crl" "this" {
  crl             = var.crl
  http_url        = var.http_url
  last_updated    = var.last_updated
  ldap_password   = var.ldap_password
  ldap_server     = var.ldap_server
  ldap_username   = var.ldap_username
  name            = var.name
  range           = var.range
  scep_cert       = var.scep_cert
  scep_url        = var.scep_url
  source          = var.source
  source_ip       = var.source_ip
  update_interval = var.update_interval
  update_vdom     = var.update_vdom
}
```

[top](#index)

### Outputs

```terraform
output "crl" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.crl
}

output "http_url" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.http_url
}

output "id" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.id
}

output "last_updated" {
  description = "returns a number"
  value       = fortios_certificate_crl.this.last_updated
}

output "ldap_server" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.ldap_server
}

output "ldap_username" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.ldap_username
}

output "range" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.range
}

output "scep_cert" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.scep_cert
}

output "scep_url" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.scep_url
}

output "source" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.source
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.source_ip
}

output "update_interval" {
  description = "returns a number"
  value       = fortios_certificate_crl.this.update_interval
}

output "update_vdom" {
  description = "returns a string"
  value       = fortios_certificate_crl.this.update_vdom
}

output "this" {
  value = fortios_certificate_crl.this
}
```

[top](#index)