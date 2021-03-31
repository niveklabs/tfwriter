# fortios_vpncertificate_setting

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
module "fortios_vpncertificate_setting" {
  source = "./modules/fortios/r/fortios_vpncertificate_setting"

  # certname_dsa1024 - (required) is a type of string
  certname_dsa1024 = null
  # certname_dsa2048 - (required) is a type of string
  certname_dsa2048 = null
  # certname_ecdsa256 - (required) is a type of string
  certname_ecdsa256 = null
  # certname_ecdsa384 - (required) is a type of string
  certname_ecdsa384 = null
  # certname_ecdsa521 - (optional) is a type of string
  certname_ecdsa521 = null
  # certname_ed25519 - (optional) is a type of string
  certname_ed25519 = null
  # certname_ed448 - (optional) is a type of string
  certname_ed448 = null
  # certname_rsa1024 - (required) is a type of string
  certname_rsa1024 = null
  # certname_rsa2048 - (required) is a type of string
  certname_rsa2048 = null
  # certname_rsa4096 - (optional) is a type of string
  certname_rsa4096 = null
  # check_ca_cert - (optional) is a type of string
  check_ca_cert = null
  # check_ca_chain - (optional) is a type of string
  check_ca_chain = null
  # cmp_key_usage_checking - (optional) is a type of string
  cmp_key_usage_checking = null
  # cmp_save_extra_certs - (optional) is a type of string
  cmp_save_extra_certs = null
  # cn_match - (optional) is a type of string
  cn_match = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # ocsp_default_server - (optional) is a type of string
  ocsp_default_server = null
  # ocsp_option - (optional) is a type of string
  ocsp_option = null
  # ocsp_status - (optional) is a type of string
  ocsp_status = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # ssl_ocsp_source_ip - (optional) is a type of string
  ssl_ocsp_source_ip = null
  # strict_crl_check - (optional) is a type of string
  strict_crl_check = null
  # strict_ocsp_check - (optional) is a type of string
  strict_ocsp_check = null
  # subject_match - (optional) is a type of string
  subject_match = null
}
```

[top](#index)

### Variables

```terraform
variable "certname_dsa1024" {
  description = "(required)"
  type        = string
}

variable "certname_dsa2048" {
  description = "(required)"
  type        = string
}

variable "certname_ecdsa256" {
  description = "(required)"
  type        = string
}

variable "certname_ecdsa384" {
  description = "(required)"
  type        = string
}

variable "certname_ecdsa521" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certname_ed25519" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certname_ed448" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certname_rsa1024" {
  description = "(required)"
  type        = string
}

variable "certname_rsa2048" {
  description = "(required)"
  type        = string
}

variable "certname_rsa4096" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_ca_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cmp_key_usage_checking" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cmp_save_extra_certs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cn_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocsp_default_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocsp_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocsp_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_ocsp_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_crl_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strict_ocsp_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_match" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpncertificate_setting" "this" {
  certname_dsa1024        = var.certname_dsa1024
  certname_dsa2048        = var.certname_dsa2048
  certname_ecdsa256       = var.certname_ecdsa256
  certname_ecdsa384       = var.certname_ecdsa384
  certname_ecdsa521       = var.certname_ecdsa521
  certname_ed25519        = var.certname_ed25519
  certname_ed448          = var.certname_ed448
  certname_rsa1024        = var.certname_rsa1024
  certname_rsa2048        = var.certname_rsa2048
  certname_rsa4096        = var.certname_rsa4096
  check_ca_cert           = var.check_ca_cert
  check_ca_chain          = var.check_ca_chain
  cmp_key_usage_checking  = var.cmp_key_usage_checking
  cmp_save_extra_certs    = var.cmp_save_extra_certs
  cn_match                = var.cn_match
  interface               = var.interface
  interface_select_method = var.interface_select_method
  ocsp_default_server     = var.ocsp_default_server
  ocsp_option             = var.ocsp_option
  ocsp_status             = var.ocsp_status
  ssl_min_proto_version   = var.ssl_min_proto_version
  ssl_ocsp_source_ip      = var.ssl_ocsp_source_ip
  strict_crl_check        = var.strict_crl_check
  strict_ocsp_check       = var.strict_ocsp_check
  subject_match           = var.subject_match
}
```

[top](#index)

### Outputs

```terraform
output "certname_ecdsa521" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.certname_ecdsa521
}

output "certname_ed25519" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.certname_ed25519
}

output "certname_ed448" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.certname_ed448
}

output "certname_rsa4096" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.certname_rsa4096
}

output "check_ca_cert" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.check_ca_cert
}

output "check_ca_chain" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.check_ca_chain
}

output "cmp_key_usage_checking" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.cmp_key_usage_checking
}

output "cmp_save_extra_certs" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.cmp_save_extra_certs
}

output "cn_match" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.cn_match
}

output "id" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.interface_select_method
}

output "ocsp_default_server" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.ocsp_default_server
}

output "ocsp_option" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.ocsp_option
}

output "ocsp_status" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.ocsp_status
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.ssl_min_proto_version
}

output "ssl_ocsp_source_ip" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.ssl_ocsp_source_ip
}

output "strict_crl_check" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.strict_crl_check
}

output "strict_ocsp_check" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.strict_ocsp_check
}

output "subject_match" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.subject_match
}

output "this" {
  value = fortios_vpncertificate_setting.this
}
```

[top](#index)