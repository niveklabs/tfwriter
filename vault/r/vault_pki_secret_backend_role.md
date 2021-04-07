# vault_pki_secret_backend_role

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
module "vault_pki_secret_backend_role" {
  source = "./modules/vault/r/vault_pki_secret_backend_role"

  # allow_any_name - (optional) is a type of bool
  allow_any_name = null
  # allow_bare_domains - (optional) is a type of bool
  allow_bare_domains = null
  # allow_glob_domains - (optional) is a type of bool
  allow_glob_domains = null
  # allow_ip_sans - (optional) is a type of bool
  allow_ip_sans = null
  # allow_localhost - (optional) is a type of bool
  allow_localhost = null
  # allow_subdomains - (optional) is a type of bool
  allow_subdomains = null
  # allowed_domains - (optional) is a type of list of string
  allowed_domains = []
  # allowed_domains_template - (optional) is a type of bool
  allowed_domains_template = null
  # allowed_other_sans - (optional) is a type of list of string
  allowed_other_sans = []
  # allowed_uri_sans - (optional) is a type of list of string
  allowed_uri_sans = []
  # backend - (required) is a type of string
  backend = null
  # basic_constraints_valid_for_non_ca - (optional) is a type of bool
  basic_constraints_valid_for_non_ca = null
  # client_flag - (optional) is a type of bool
  client_flag = null
  # code_signing_flag - (optional) is a type of bool
  code_signing_flag = null
  # country - (optional) is a type of list of string
  country = []
  # email_protection_flag - (optional) is a type of bool
  email_protection_flag = null
  # enforce_hostnames - (optional) is a type of bool
  enforce_hostnames = null
  # ext_key_usage - (optional) is a type of list of string
  ext_key_usage = []
  # generate_lease - (optional) is a type of bool
  generate_lease = null
  # key_bits - (optional) is a type of number
  key_bits = null
  # key_type - (optional) is a type of string
  key_type = null
  # key_usage - (optional) is a type of list of string
  key_usage = []
  # locality - (optional) is a type of list of string
  locality = []
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # no_store - (optional) is a type of bool
  no_store = null
  # not_before_duration - (optional) is a type of string
  not_before_duration = null
  # organization - (optional) is a type of list of string
  organization = []
  # ou - (optional) is a type of list of string
  ou = []
  # policy_identifiers - (optional) is a type of list of string
  policy_identifiers = []
  # postal_code - (optional) is a type of list of string
  postal_code = []
  # province - (optional) is a type of list of string
  province = []
  # require_cn - (optional) is a type of bool
  require_cn = null
  # server_flag - (optional) is a type of bool
  server_flag = null
  # street_address - (optional) is a type of list of string
  street_address = []
  # ttl - (optional) is a type of string
  ttl = null
  # use_csr_common_name - (optional) is a type of bool
  use_csr_common_name = null
  # use_csr_sans - (optional) is a type of bool
  use_csr_sans = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_any_name" {
  description = "(optional) - Flag to allow any name"
  type        = bool
  default     = null
}

variable "allow_bare_domains" {
  description = "(optional) - Flag to allow certificates matching the actual domain."
  type        = bool
  default     = null
}

variable "allow_glob_domains" {
  description = "(optional) - Flag to allow names containing glob patterns."
  type        = bool
  default     = null
}

variable "allow_ip_sans" {
  description = "(optional) - Flag to allow IP SANs"
  type        = bool
  default     = null
}

variable "allow_localhost" {
  description = "(optional) - Flag to allow certificates for localhost."
  type        = bool
  default     = null
}

variable "allow_subdomains" {
  description = "(optional) - Flag to allow certificates matching subdomains."
  type        = bool
  default     = null
}

variable "allowed_domains" {
  description = "(optional) - The domains of the role."
  type        = list(string)
  default     = null
}

variable "allowed_domains_template" {
  description = "(optional) - Flag to indicate that `allowed_domains` specifies a template expression (e.g. {{identity.entity.aliases.<mount accessor>.name}})"
  type        = bool
  default     = null
}

variable "allowed_other_sans" {
  description = "(optional) - Defines allowed custom SANs"
  type        = list(string)
  default     = null
}

variable "allowed_uri_sans" {
  description = "(optional) - Defines allowed URI SANs"
  type        = list(string)
  default     = null
}

variable "backend" {
  description = "(required) - The path of the PKI secret backend the resource belongs to."
  type        = string
}

variable "basic_constraints_valid_for_non_ca" {
  description = "(optional) - Flag to mark basic constraints valid when issuing non-CA certificates."
  type        = bool
  default     = null
}

variable "client_flag" {
  description = "(optional) - Flag to specify certificates for client use."
  type        = bool
  default     = null
}

variable "code_signing_flag" {
  description = "(optional) - Flag to specify certificates for code signing use."
  type        = bool
  default     = null
}

variable "country" {
  description = "(optional) - The country of generated certificates."
  type        = list(string)
  default     = null
}

variable "email_protection_flag" {
  description = "(optional) - Flag to specify certificates for email protection use."
  type        = bool
  default     = null
}

variable "enforce_hostnames" {
  description = "(optional) - Flag to allow only valid host names"
  type        = bool
  default     = null
}

variable "ext_key_usage" {
  description = "(optional) - Specify the allowed extended key usage constraint on issued certificates."
  type        = list(string)
  default     = null
}

variable "generate_lease" {
  description = "(optional) - Flag to generate leases with certificates."
  type        = bool
  default     = null
}

variable "key_bits" {
  description = "(optional) - The number of bits of generated keys."
  type        = number
  default     = null
}

variable "key_type" {
  description = "(optional) - The type of generated keys."
  type        = string
  default     = null
}

variable "key_usage" {
  description = "(optional) - Specify the allowed key usage constraint on issued certificates."
  type        = list(string)
  default     = null
}

variable "locality" {
  description = "(optional) - The locality of generated certificates."
  type        = list(string)
  default     = null
}

variable "max_ttl" {
  description = "(optional) - The maximum TTL."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name for the role."
  type        = string
}

variable "no_store" {
  description = "(optional) - Flag to not store certificates in the storage backend."
  type        = bool
  default     = null
}

variable "not_before_duration" {
  description = "(optional) - Specifies the duration by which to backdate the NotBefore property."
  type        = string
  default     = null
}

variable "organization" {
  description = "(optional) - The organization of generated certificates."
  type        = list(string)
  default     = null
}

variable "ou" {
  description = "(optional) - The organization unit of generated certificates."
  type        = list(string)
  default     = null
}

variable "policy_identifiers" {
  description = "(optional) - Specify the list of allowed policies IODs."
  type        = list(string)
  default     = null
}

variable "postal_code" {
  description = "(optional) - The postal code of generated certificates."
  type        = list(string)
  default     = null
}

variable "province" {
  description = "(optional) - The province of generated certificates."
  type        = list(string)
  default     = null
}

variable "require_cn" {
  description = "(optional) - Flag to force CN usage."
  type        = bool
  default     = null
}

variable "server_flag" {
  description = "(optional) - Flag to specify certificates for server use."
  type        = bool
  default     = null
}

variable "street_address" {
  description = "(optional) - The street address of generated certificates."
  type        = list(string)
  default     = null
}

variable "ttl" {
  description = "(optional) - The TTL."
  type        = string
  default     = null
}

variable "use_csr_common_name" {
  description = "(optional) - Flag to use the CN in the CSR."
  type        = bool
  default     = null
}

variable "use_csr_sans" {
  description = "(optional) - Flag to use the SANs in the CSR."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_role" "this" {
  # allow_any_name - (optional) is a type of bool
  allow_any_name = var.allow_any_name
  # allow_bare_domains - (optional) is a type of bool
  allow_bare_domains = var.allow_bare_domains
  # allow_glob_domains - (optional) is a type of bool
  allow_glob_domains = var.allow_glob_domains
  # allow_ip_sans - (optional) is a type of bool
  allow_ip_sans = var.allow_ip_sans
  # allow_localhost - (optional) is a type of bool
  allow_localhost = var.allow_localhost
  # allow_subdomains - (optional) is a type of bool
  allow_subdomains = var.allow_subdomains
  # allowed_domains - (optional) is a type of list of string
  allowed_domains = var.allowed_domains
  # allowed_domains_template - (optional) is a type of bool
  allowed_domains_template = var.allowed_domains_template
  # allowed_other_sans - (optional) is a type of list of string
  allowed_other_sans = var.allowed_other_sans
  # allowed_uri_sans - (optional) is a type of list of string
  allowed_uri_sans = var.allowed_uri_sans
  # backend - (required) is a type of string
  backend = var.backend
  # basic_constraints_valid_for_non_ca - (optional) is a type of bool
  basic_constraints_valid_for_non_ca = var.basic_constraints_valid_for_non_ca
  # client_flag - (optional) is a type of bool
  client_flag = var.client_flag
  # code_signing_flag - (optional) is a type of bool
  code_signing_flag = var.code_signing_flag
  # country - (optional) is a type of list of string
  country = var.country
  # email_protection_flag - (optional) is a type of bool
  email_protection_flag = var.email_protection_flag
  # enforce_hostnames - (optional) is a type of bool
  enforce_hostnames = var.enforce_hostnames
  # ext_key_usage - (optional) is a type of list of string
  ext_key_usage = var.ext_key_usage
  # generate_lease - (optional) is a type of bool
  generate_lease = var.generate_lease
  # key_bits - (optional) is a type of number
  key_bits = var.key_bits
  # key_type - (optional) is a type of string
  key_type = var.key_type
  # key_usage - (optional) is a type of list of string
  key_usage = var.key_usage
  # locality - (optional) is a type of list of string
  locality = var.locality
  # max_ttl - (optional) is a type of string
  max_ttl = var.max_ttl
  # name - (required) is a type of string
  name = var.name
  # no_store - (optional) is a type of bool
  no_store = var.no_store
  # not_before_duration - (optional) is a type of string
  not_before_duration = var.not_before_duration
  # organization - (optional) is a type of list of string
  organization = var.organization
  # ou - (optional) is a type of list of string
  ou = var.ou
  # policy_identifiers - (optional) is a type of list of string
  policy_identifiers = var.policy_identifiers
  # postal_code - (optional) is a type of list of string
  postal_code = var.postal_code
  # province - (optional) is a type of list of string
  province = var.province
  # require_cn - (optional) is a type of bool
  require_cn = var.require_cn
  # server_flag - (optional) is a type of bool
  server_flag = var.server_flag
  # street_address - (optional) is a type of list of string
  street_address = var.street_address
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # use_csr_common_name - (optional) is a type of bool
  use_csr_common_name = var.use_csr_common_name
  # use_csr_sans - (optional) is a type of bool
  use_csr_sans = var.use_csr_sans
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_role.this.id
}

output "not_before_duration" {
  description = "returns a string"
  value       = vault_pki_secret_backend_role.this.not_before_duration
}

output "this" {
  value = vault_pki_secret_backend_role.this
}
```

[top](#index)