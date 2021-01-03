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
    fortios = ">= 1.6.18"
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
  # certname_rsa1024 - (required) is a type of string
  certname_rsa1024 = null
  # certname_rsa2048 - (required) is a type of string
  certname_rsa2048 = null
  # check_ca_cert - (optional) is a type of string
  check_ca_cert = null
  # check_ca_chain - (optional) is a type of string
  check_ca_chain = null
  # cmp_save_extra_certs - (optional) is a type of string
  cmp_save_extra_certs = null
  # cn_match - (optional) is a type of string
  cn_match = null
  # ocsp_default_server - (optional) is a type of string
  ocsp_default_server = null
  # ocsp_option - (optional) is a type of string
  ocsp_option = null
  # ocsp_status - (optional) is a type of string
  ocsp_status = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
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

variable "certname_rsa1024" {
  description = "(required)"
  type        = string
}

variable "certname_rsa2048" {
  description = "(required)"
  type        = string
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
  certname_dsa1024      = var.certname_dsa1024
  certname_dsa2048      = var.certname_dsa2048
  certname_ecdsa256     = var.certname_ecdsa256
  certname_ecdsa384     = var.certname_ecdsa384
  certname_rsa1024      = var.certname_rsa1024
  certname_rsa2048      = var.certname_rsa2048
  check_ca_cert         = var.check_ca_cert
  check_ca_chain        = var.check_ca_chain
  cmp_save_extra_certs  = var.cmp_save_extra_certs
  cn_match              = var.cn_match
  ocsp_default_server   = var.ocsp_default_server
  ocsp_option           = var.ocsp_option
  ocsp_status           = var.ocsp_status
  ssl_min_proto_version = var.ssl_min_proto_version
  strict_crl_check      = var.strict_crl_check
  strict_ocsp_check     = var.strict_ocsp_check
  subject_match         = var.subject_match
}
```

[top](#index)

### Outputs

```terraform
output "check_ca_cert" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.check_ca_cert
}

output "check_ca_chain" {
  description = "returns a string"
  value       = fortios_vpncertificate_setting.this.check_ca_chain
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