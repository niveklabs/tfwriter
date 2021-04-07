# vault_pki_secret_backend_sign

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_pki_secret_backend_sign" {
  source = "./modules/vault/r/vault_pki_secret_backend_sign"

  # alt_names - (optional) is a type of list of string
  alt_names = []
  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # backend - (required) is a type of string
  backend = null
  # common_name - (required) is a type of string
  common_name = null
  # csr - (required) is a type of string
  csr = null
  # exclude_cn_from_sans - (optional) is a type of bool
  exclude_cn_from_sans = null
  # format - (optional) is a type of string
  format = null
  # ip_sans - (optional) is a type of list of string
  ip_sans = []
  # min_seconds_remaining - (optional) is a type of number
  min_seconds_remaining = null
  # name - (required) is a type of string
  name = null
  # other_sans - (optional) is a type of list of string
  other_sans = []
  # ttl - (optional) is a type of string
  ttl = null
  # uri_sans - (optional) is a type of list of string
  uri_sans = []
}
```

[top](#index)

### Variables

```terraform
variable "alt_names" {
  description = "(optional) - List of alternative names."
  type        = list(string)
  default     = null
}

variable "auto_renew" {
  description = "(optional) - If enabled, a new certificate will be generated if the expiration is within min_seconds_remaining"
  type        = bool
  default     = null
}

variable "backend" {
  description = "(required) - The PKI secret backend the resource belongs to."
  type        = string
}

variable "common_name" {
  description = "(required) - CN of intermediate to create."
  type        = string
}

variable "csr" {
  description = "(required) - The CSR."
  type        = string
}

variable "exclude_cn_from_sans" {
  description = "(optional) - Flag to exclude CN from SANs."
  type        = bool
  default     = null
}

variable "format" {
  description = "(optional) - The format of data."
  type        = string
  default     = null
}

variable "ip_sans" {
  description = "(optional) - List of alternative IPs."
  type        = list(string)
  default     = null
}

variable "min_seconds_remaining" {
  description = "(optional) - Generate a new certificate when the expiration is within this number of seconds"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the role to create the certificate against."
  type        = string
}

variable "other_sans" {
  description = "(optional) - List of other SANs."
  type        = list(string)
  default     = null
}

variable "ttl" {
  description = "(optional) - Time to live."
  type        = string
  default     = null
}

variable "uri_sans" {
  description = "(optional) - List of alterative URIs."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_sign" "this" {
  # alt_names - (optional) is a type of list of string
  alt_names = var.alt_names
  # auto_renew - (optional) is a type of bool
  auto_renew = var.auto_renew
  # backend - (required) is a type of string
  backend = var.backend
  # common_name - (required) is a type of string
  common_name = var.common_name
  # csr - (required) is a type of string
  csr = var.csr
  # exclude_cn_from_sans - (optional) is a type of bool
  exclude_cn_from_sans = var.exclude_cn_from_sans
  # format - (optional) is a type of string
  format = var.format
  # ip_sans - (optional) is a type of list of string
  ip_sans = var.ip_sans
  # min_seconds_remaining - (optional) is a type of number
  min_seconds_remaining = var.min_seconds_remaining
  # name - (required) is a type of string
  name = var.name
  # other_sans - (optional) is a type of list of string
  other_sans = var.other_sans
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # uri_sans - (optional) is a type of list of string
  uri_sans = var.uri_sans
}
```

[top](#index)

### Outputs

```terraform
output "ca_chain" {
  description = "returns a list of string"
  value       = vault_pki_secret_backend_sign.this.ca_chain
}

output "certificate" {
  description = "returns a string"
  value       = vault_pki_secret_backend_sign.this.certificate
}

output "expiration" {
  description = "returns a number"
  value       = vault_pki_secret_backend_sign.this.expiration
}

output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_sign.this.id
}

output "issuing_ca" {
  description = "returns a string"
  value       = vault_pki_secret_backend_sign.this.issuing_ca
}

output "serial" {
  description = "returns a string"
  value       = vault_pki_secret_backend_sign.this.serial
}

output "this" {
  value = vault_pki_secret_backend_sign.this
}
```

[top](#index)