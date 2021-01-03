# fortios_certificate_local

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_certificate_local" {
  source = null

  # auto_regenerate_days - (optional) is a type of number
  auto_regenerate_days = null
  # auto_regenerate_days_warning - (optional) is a type of number
  auto_regenerate_days_warning = null
  # ca_identifier - (optional) is a type of string
  ca_identifier = null
  # certificate - (optional) is a type of string
  certificate = null
  # cmp_path - (optional) is a type of string
  cmp_path = null
  # cmp_regeneration_method - (optional) is a type of string
  cmp_regeneration_method = null
  # cmp_server - (optional) is a type of string
  cmp_server = null
  # cmp_server_cert - (optional) is a type of string
  cmp_server_cert = null
  # comments - (optional) is a type of string
  comments = null
  # csr - (optional) is a type of string
  csr = null
  # enroll_protocol - (optional) is a type of string
  enroll_protocol = null
  # ike_localid - (optional) is a type of string
  ike_localid = null
  # ike_localid_type - (optional) is a type of string
  ike_localid_type = null
  # last_updated - (optional) is a type of number
  last_updated = null
  # name - (required) is a type of string
  name = null
  # name_encoding - (optional) is a type of string
  name_encoding = null
  # password - (optional) is a type of string
  password = null
  # private_key - (required) is a type of string
  private_key = null
  # range - (optional) is a type of string
  range = null
  # scep_password - (optional) is a type of string
  scep_password = null
  # scep_url - (optional) is a type of string
  scep_url = null
  # source - (optional) is a type of string
  # source_ip - (optional) is a type of string
  source_ip = null
  # state - (optional) is a type of string
  state = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_regenerate_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_regenerate_days_warning" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ca_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cmp_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cmp_regeneration_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cmp_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cmp_server_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "csr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enroll_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ike_localid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ike_localid_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_updated" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scep_password" {
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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_certificate_local" "this" {
  auto_regenerate_days         = var.auto_regenerate_days
  auto_regenerate_days_warning = var.auto_regenerate_days_warning
  ca_identifier                = var.ca_identifier
  certificate                  = var.certificate
  cmp_path                     = var.cmp_path
  cmp_regeneration_method      = var.cmp_regeneration_method
  cmp_server                   = var.cmp_server
  cmp_server_cert              = var.cmp_server_cert
  comments                     = var.comments
  csr                          = var.csr
  enroll_protocol              = var.enroll_protocol
  ike_localid                  = var.ike_localid
  ike_localid_type             = var.ike_localid_type
  last_updated                 = var.last_updated
  name                         = var.name
  name_encoding                = var.name_encoding
  password                     = var.password
  private_key                  = var.private_key
  range                        = var.range
  scep_password                = var.scep_password
  scep_url                     = var.scep_url
  source                       = var.source
  source_ip                    = var.source_ip
  state                        = var.state
}
```

[top](#index)

### Outputs

```terraform
output "auto_regenerate_days" {
  description = "returns a number"
  value       = fortios_certificate_local.this.auto_regenerate_days
}

output "auto_regenerate_days_warning" {
  description = "returns a number"
  value       = fortios_certificate_local.this.auto_regenerate_days_warning
}

output "ca_identifier" {
  description = "returns a string"
  value       = fortios_certificate_local.this.ca_identifier
}

output "certificate" {
  description = "returns a string"
  value       = fortios_certificate_local.this.certificate
}

output "cmp_path" {
  description = "returns a string"
  value       = fortios_certificate_local.this.cmp_path
}

output "cmp_regeneration_method" {
  description = "returns a string"
  value       = fortios_certificate_local.this.cmp_regeneration_method
}

output "cmp_server" {
  description = "returns a string"
  value       = fortios_certificate_local.this.cmp_server
}

output "cmp_server_cert" {
  description = "returns a string"
  value       = fortios_certificate_local.this.cmp_server_cert
}

output "comments" {
  description = "returns a string"
  value       = fortios_certificate_local.this.comments
}

output "csr" {
  description = "returns a string"
  value       = fortios_certificate_local.this.csr
}

output "enroll_protocol" {
  description = "returns a string"
  value       = fortios_certificate_local.this.enroll_protocol
}

output "id" {
  description = "returns a string"
  value       = fortios_certificate_local.this.id
}

output "ike_localid" {
  description = "returns a string"
  value       = fortios_certificate_local.this.ike_localid
}

output "ike_localid_type" {
  description = "returns a string"
  value       = fortios_certificate_local.this.ike_localid_type
}

output "last_updated" {
  description = "returns a number"
  value       = fortios_certificate_local.this.last_updated
}

output "name_encoding" {
  description = "returns a string"
  value       = fortios_certificate_local.this.name_encoding
}

output "range" {
  description = "returns a string"
  value       = fortios_certificate_local.this.range
}

output "scep_url" {
  description = "returns a string"
  value       = fortios_certificate_local.this.scep_url
}

output "source" {
  description = "returns a string"
  value       = fortios_certificate_local.this.source
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_certificate_local.this.source_ip
}

output "state" {
  description = "returns a string"
  value       = fortios_certificate_local.this.state
}

output "this" {
  value = fortios_certificate_local.this
}
```

[top](#index)