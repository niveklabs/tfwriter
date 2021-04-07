# vault_cert_auth_backend_role

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
module "vault_cert_auth_backend_role" {
  source = "./modules/vault/r/vault_cert_auth_backend_role"

  # allowed_common_names - (optional) is a type of set of string
  allowed_common_names = []
  # allowed_dns_sans - (optional) is a type of set of string
  allowed_dns_sans = []
  # allowed_email_sans - (optional) is a type of set of string
  allowed_email_sans = []
  # allowed_names - (optional) is a type of set of string
  allowed_names = []
  # allowed_organization_units - (optional) is a type of set of string
  allowed_organization_units = []
  # allowed_uri_sans - (optional) is a type of set of string
  allowed_uri_sans = []
  # backend - (optional) is a type of string
  backend = null
  # bound_cidrs - (optional) is a type of set of string
  bound_cidrs = []
  # certificate - (required) is a type of string
  certificate = null
  # display_name - (optional) is a type of string
  display_name = null
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # period - (optional) is a type of string
  period = null
  # policies - (optional) is a type of set of string
  policies = []
  # required_extensions - (optional) is a type of set of string
  required_extensions = []
  # token_bound_cidrs - (optional) is a type of set of string
  token_bound_cidrs = []
  # token_explicit_max_ttl - (optional) is a type of number
  token_explicit_max_ttl = null
  # token_max_ttl - (optional) is a type of number
  token_max_ttl = null
  # token_no_default_policy - (optional) is a type of bool
  token_no_default_policy = null
  # token_num_uses - (optional) is a type of number
  token_num_uses = null
  # token_period - (optional) is a type of number
  token_period = null
  # token_policies - (optional) is a type of set of string
  token_policies = []
  # token_ttl - (optional) is a type of number
  token_ttl = null
  # token_type - (optional) is a type of string
  token_type = null
  # ttl - (optional) is a type of string
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_common_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "allowed_dns_sans" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "allowed_email_sans" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "allowed_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "allowed_organization_units" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "allowed_uri_sans" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backend" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bound_cidrs" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "certificate" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "required_extensions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "token_bound_cidrs" {
  description = "(optional) - Specifies the blocks of IP addresses which are allowed to use the generated token"
  type        = set(string)
  default     = null
}

variable "token_explicit_max_ttl" {
  description = "(optional) - Generated Token's Explicit Maximum TTL in seconds"
  type        = number
  default     = null
}

variable "token_max_ttl" {
  description = "(optional) - The maximum lifetime of the generated token"
  type        = number
  default     = null
}

variable "token_no_default_policy" {
  description = "(optional) - If true, the 'default' policy will not automatically be added to generated tokens"
  type        = bool
  default     = null
}

variable "token_num_uses" {
  description = "(optional) - The maximum number of times a token may be used, a value of zero means unlimited"
  type        = number
  default     = null
}

variable "token_period" {
  description = "(optional) - Generated Token's Period"
  type        = number
  default     = null
}

variable "token_policies" {
  description = "(optional) - Generated Token's Policies"
  type        = set(string)
  default     = null
}

variable "token_ttl" {
  description = "(optional) - The initial ttl of the token to generate in seconds"
  type        = number
  default     = null
}

variable "token_type" {
  description = "(optional) - The type of token to generate, service or batch"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_cert_auth_backend_role" "this" {
  # allowed_common_names - (optional) is a type of set of string
  allowed_common_names = var.allowed_common_names
  # allowed_dns_sans - (optional) is a type of set of string
  allowed_dns_sans = var.allowed_dns_sans
  # allowed_email_sans - (optional) is a type of set of string
  allowed_email_sans = var.allowed_email_sans
  # allowed_names - (optional) is a type of set of string
  allowed_names = var.allowed_names
  # allowed_organization_units - (optional) is a type of set of string
  allowed_organization_units = var.allowed_organization_units
  # allowed_uri_sans - (optional) is a type of set of string
  allowed_uri_sans = var.allowed_uri_sans
  # backend - (optional) is a type of string
  backend = var.backend
  # bound_cidrs - (optional) is a type of set of string
  bound_cidrs = var.bound_cidrs
  # certificate - (required) is a type of string
  certificate = var.certificate
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # max_ttl - (optional) is a type of string
  max_ttl = var.max_ttl
  # name - (required) is a type of string
  name = var.name
  # period - (optional) is a type of string
  period = var.period
  # policies - (optional) is a type of set of string
  policies = var.policies
  # required_extensions - (optional) is a type of set of string
  required_extensions = var.required_extensions
  # token_bound_cidrs - (optional) is a type of set of string
  token_bound_cidrs = var.token_bound_cidrs
  # token_explicit_max_ttl - (optional) is a type of number
  token_explicit_max_ttl = var.token_explicit_max_ttl
  # token_max_ttl - (optional) is a type of number
  token_max_ttl = var.token_max_ttl
  # token_no_default_policy - (optional) is a type of bool
  token_no_default_policy = var.token_no_default_policy
  # token_num_uses - (optional) is a type of number
  token_num_uses = var.token_num_uses
  # token_period - (optional) is a type of number
  token_period = var.token_period
  # token_policies - (optional) is a type of set of string
  token_policies = var.token_policies
  # token_ttl - (optional) is a type of number
  token_ttl = var.token_ttl
  # token_type - (optional) is a type of string
  token_type = var.token_type
  # ttl - (optional) is a type of string
  ttl = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "allowed_common_names" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.allowed_common_names
}

output "allowed_dns_sans" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.allowed_dns_sans
}

output "allowed_email_sans" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.allowed_email_sans
}

output "allowed_names" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.allowed_names
}

output "allowed_organization_units" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.allowed_organization_units
}

output "allowed_uri_sans" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.allowed_uri_sans
}

output "bound_cidrs" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.bound_cidrs
}

output "display_name" {
  description = "returns a string"
  value       = vault_cert_auth_backend_role.this.display_name
}

output "id" {
  description = "returns a string"
  value       = vault_cert_auth_backend_role.this.id
}

output "max_ttl" {
  description = "returns a string"
  value       = vault_cert_auth_backend_role.this.max_ttl
}

output "period" {
  description = "returns a string"
  value       = vault_cert_auth_backend_role.this.period
}

output "policies" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.policies
}

output "required_extensions" {
  description = "returns a set of string"
  value       = vault_cert_auth_backend_role.this.required_extensions
}

output "ttl" {
  description = "returns a string"
  value       = vault_cert_auth_backend_role.this.ttl
}

output "this" {
  value = vault_cert_auth_backend_role.this
}
```

[top](#index)