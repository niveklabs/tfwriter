# vault_pki_secret_backend_root_sign_intermediate

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
module "vault_pki_secret_backend_root_sign_intermediate" {
  source = "./modules/vault/r/vault_pki_secret_backend_root_sign_intermediate"

  # alt_names - (optional) is a type of list of string
  alt_names = []
  # backend - (required) is a type of string
  backend = null
  # common_name - (required) is a type of string
  common_name = null
  # country - (optional) is a type of string
  country = null
  # csr - (required) is a type of string
  csr = null
  # exclude_cn_from_sans - (optional) is a type of bool
  exclude_cn_from_sans = null
  # format - (optional) is a type of string
  format = null
  # ip_sans - (optional) is a type of list of string
  ip_sans = []
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
  # province - (optional) is a type of string
  province = null
  # street_address - (optional) is a type of string
  street_address = null
  # ttl - (optional) is a type of string
  ttl = null
  # uri_sans - (optional) is a type of list of string
  uri_sans = []
  # use_csr_values - (optional) is a type of bool
  use_csr_values = null
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

variable "uri_sans" {
  description = "(optional) - List of alterative URIs."
  type        = list(string)
  default     = null
}

variable "use_csr_values" {
  description = "(optional) - Preserve CSR values."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_root_sign_intermediate" "this" {
  # alt_names - (optional) is a type of list of string
  alt_names = var.alt_names
  # backend - (required) is a type of string
  backend = var.backend
  # common_name - (required) is a type of string
  common_name = var.common_name
  # country - (optional) is a type of string
  country = var.country
  # csr - (required) is a type of string
  csr = var.csr
  # exclude_cn_from_sans - (optional) is a type of bool
  exclude_cn_from_sans = var.exclude_cn_from_sans
  # format - (optional) is a type of string
  format = var.format
  # ip_sans - (optional) is a type of list of string
  ip_sans = var.ip_sans
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
  # province - (optional) is a type of string
  province = var.province
  # street_address - (optional) is a type of string
  street_address = var.street_address
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # uri_sans - (optional) is a type of list of string
  uri_sans = var.uri_sans
  # use_csr_values - (optional) is a type of bool
  use_csr_values = var.use_csr_values
}
```

[top](#index)

### Outputs

```terraform
output "ca_chain" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_sign_intermediate.this.ca_chain
}

output "certificate" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_sign_intermediate.this.certificate
}

output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_sign_intermediate.this.id
}

output "issuing_ca" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_sign_intermediate.this.issuing_ca
}

output "serial" {
  description = "returns a string"
  value       = vault_pki_secret_backend_root_sign_intermediate.this.serial
}

output "this" {
  value = vault_pki_secret_backend_root_sign_intermediate.this
}
```

[top](#index)