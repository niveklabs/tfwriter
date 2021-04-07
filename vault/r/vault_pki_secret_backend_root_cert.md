# vault_pki_secret_backend_root_cert

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
module "vault_pki_secret_backend_root_cert" {
  source = "./modules/vault/r/vault_pki_secret_backend_root_cert"

  # alt_names - (optional) is a type of list of string
  alt_names = []
  # backend - (required) is a type of string
  backend = null
  # common_name - (required) is a type of string
  common_name = null
  # country - (optional) is a type of string
  country = null
  # exclude_cn_from_sans - (optional) is a type of bool
  exclude_cn_from_sans = null
  # format - (optional) is a type of string
  format = null
  # ip_sans - (optional) is a type of list of string
  ip_sans = []
  # key_bits - (optional) is a type of number
  key_bits = null
  # key_type - (optional) is a type of string
  key_type = null
  # locality - (optional) is a type of string
  locality = null
  # max_path_length - (optional) is a type of number
  max_path_length = null
  # organization - (optional) is a type of string
  organization = null
  # other_sans - (optional) is a type of list of string
  other_sans = []
  # ou - (optional) is a type of string
  ou = null
  # permitted_dns_domains - (optional) is a type of list of string
  permitted_dns_domains = []
  # postal_code - (optional) is a type of string
  postal_code = null
  # private_key_format - (optional) is a type of string
  private_key_format = null
  # province - (optional) is a type of string
  province = null
  # street_address - (optional) is a type of string
  street_address = null
  # ttl - (optional) is a type of string
  ttl = null
  # type - (required) is a type of string
  type = null
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

variable "backend" {
  description = "(required) - The PKI secret backend the resource belongs to."
  type        = string
}

variable "common_name" {
  description = "(required) - CN of intermediate to create."
  type        = string
}

variable "country" {
  description = "(optional) - The country."
  type        = string
  default     = null
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

variable "key_bits" {
  description = "(optional) - The number of bits to use."
  type        = number
  default     = null
}

variable "key_type" {
  description = "(optional) - The desired key type."
  type        = string
  default     = null
}

variable "locality" {
  description = "(optional) - The locality."
  type        = string
  default     = null
}

variable "max_path_length" {
  description = "(optional) - The maximum path length to encode in the generated certificate."
  type        = number
  default     = null
}

variable "organization" {
  description = "(optional) - The organization."
  type        = string
  default     = null
}

variable "other_sans" {
  description = "(optional) - List of other SANs."
  type        = list(string)
  default     = null
}

variable "ou" {
  description = "(optional) - The organization unit."
  type        = string
  default     = null
}

variable "permitted_dns_domains" {
  description = "(optional) - List of domains for which certificates are allowed to be issued."
  type        = list(string)
  default     = null
}

variable "postal_code" {
  description = "(optional) - The postal code."
  type        = string
  default     = null
}

variable "private_key_format" {
  description = "(optional) - The private key format."
  type        = string
  default     = null
}

variable "province" {
  description = "(optional) - The province."
  type        = string
  default     = null
}

variable "street_address" {
  description = "(optional) - The street address."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - Time to live."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Type of intermediate to create. Must be either \"exported\" or \"internal\"."
  type        = string
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
resource "vault_pki_secret_backend_root_cert" "this" {
  # alt_names - (optional) is a type of list of string
  alt_names = var.alt_names
  # backend - (required) is a type of string
  backend = var.backend
  # common_name - (required) is a type of string
  common_name = var.common_name
  # country - (optional) is a type of string
  country = var.country
  # exclude_cn_from_sans - (optional) is a type of bool
  exclude_cn_from_sans = var.exclude_cn_from_sans
  # format - (optional) is a type of string
  format = var.format
  # ip_sans - (optional) is a type of list of string
  ip_sans = var.ip_sans
  # key_bits - (optional) is a type of number
  key_bits = var.key_bits
  # key_type - (optional) is a type of string
  key_type = var.key_type
  # locality - (optional) is a type of string
  locality = var.locality
  # max_path_length - (optional) is a type of number
  max_path_length = var.max_path_length
  # organization - (optional) is a type of string
  organization = var.organization
  # other_sans - (optional) is a type of list of string
  other_sans = var.other_sans
  # ou - (optional) is a type of string
  ou = var.ou
  # permitted_dns_domains - (optional) is a type of list of string
  permitted_dns_domains = var.permitted_dns_domains
  # postal_code - (optional) is a type of string
  postal_code = var.postal_code
  # private_key_format - (optional) is a type of string
  private_key_format = var.private_key_format
  # province - (optional) is a type of string
  province = var.province
  # street_address - (optional) is a type of string
  street_address = var.street_address
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # uri_sans - (optional) is a type of list of string
  uri_sans = var.uri_sans
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_cert.this.certificate
}

output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_cert.this.id
}

output "issuing_ca" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_cert.this.issuing_ca
}

output "serial" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_cert.this.serial
}

output "this" {
  value = vault_pki_secret_backend_root_cert.this
}
```

[top](#index)