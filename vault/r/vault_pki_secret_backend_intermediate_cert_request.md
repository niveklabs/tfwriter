# vault_pki_secret_backend_intermediate_cert_request

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_pki_secret_backend_intermediate_cert_request" {
  source = "./modules/vault/r/vault_pki_secret_backend_intermediate_cert_request"

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
  # organization - (optional) is a type of string
  organization = null
  # other_sans - (optional) is a type of list of string
  other_sans = []
  # ou - (optional) is a type of string
  ou = null
  # postal_code - (optional) is a type of string
  postal_code = null
  # private_key_format - (optional) is a type of string
  private_key_format = null
  # province - (optional) is a type of string
  province = null
  # street_address - (optional) is a type of string
  street_address = null
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

variable "type" {
  description = "(required) - Type of intermediate to create. Must be either \"exported\" or \"internal\"."
  type        = string
}

variable "uri_sans" {
  description = "(optional) - List of alternative URIs."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_intermediate_cert_request" "this" {
  alt_names            = var.alt_names
  backend              = var.backend
  common_name          = var.common_name
  country              = var.country
  exclude_cn_from_sans = var.exclude_cn_from_sans
  format               = var.format
  ip_sans              = var.ip_sans
  key_bits             = var.key_bits
  key_type             = var.key_type
  locality             = var.locality
  organization         = var.organization
  other_sans           = var.other_sans
  ou                   = var.ou
  postal_code          = var.postal_code
  private_key_format   = var.private_key_format
  province             = var.province
  street_address       = var.street_address
  type                 = var.type
  uri_sans             = var.uri_sans
}
```

[top](#index)

### Outputs

```terraform
output "csr" {
  description = "returns a string"
  value       = vault_pki_secret_backend_intermediate_cert_request.this.csr
}

output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_intermediate_cert_request.this.id
}

output "private_key" {
  description = "returns a string"
  value       = vault_pki_secret_backend_intermediate_cert_request.this.private_key
  sensitive   = true
}

output "private_key_type" {
  description = "returns a string"
  value       = vault_pki_secret_backend_intermediate_cert_request.this.private_key_type
}

output "this" {
  value = vault_pki_secret_backend_intermediate_cert_request.this
}
```

[top](#index)