# vault_ldap_auth_backend

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
module "vault_ldap_auth_backend" {
  source = "./modules/vault/r/vault_ldap_auth_backend"

  # binddn - (optional) is a type of string
  binddn = null
  # bindpass - (optional) is a type of string
  bindpass = null
  # certificate - (optional) is a type of string
  certificate = null
  # deny_null_bind - (optional) is a type of bool
  deny_null_bind = null
  # description - (optional) is a type of string
  description = null
  # discoverdn - (optional) is a type of bool
  discoverdn = null
  # groupattr - (optional) is a type of string
  groupattr = null
  # groupdn - (optional) is a type of string
  groupdn = null
  # groupfilter - (optional) is a type of string
  groupfilter = null
  # insecure_tls - (optional) is a type of bool
  insecure_tls = null
  # path - (optional) is a type of string
  path = null
  # starttls - (optional) is a type of bool
  starttls = null
  # tls_max_version - (optional) is a type of string
  tls_max_version = null
  # tls_min_version - (optional) is a type of string
  tls_min_version = null
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
  # upndomain - (optional) is a type of string
  upndomain = null
  # url - (required) is a type of string
  url = null
  # use_token_groups - (optional) is a type of bool
  use_token_groups = null
  # userattr - (optional) is a type of string
  userattr = null
  # userdn - (optional) is a type of string
  userdn = null
}
```

[top](#index)

### Variables

```terraform
variable "binddn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bindpass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deny_null_bind" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "discoverdn" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "groupattr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groupdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groupfilter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "insecure_tls" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "starttls" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tls_max_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tls_min_version" {
  description = "(optional)"
  type        = string
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

variable "upndomain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "use_token_groups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "userattr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "userdn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_ldap_auth_backend" "this" {
  # binddn - (optional) is a type of string
  binddn = var.binddn
  # bindpass - (optional) is a type of string
  bindpass = var.bindpass
  # certificate - (optional) is a type of string
  certificate = var.certificate
  # deny_null_bind - (optional) is a type of bool
  deny_null_bind = var.deny_null_bind
  # description - (optional) is a type of string
  description = var.description
  # discoverdn - (optional) is a type of bool
  discoverdn = var.discoverdn
  # groupattr - (optional) is a type of string
  groupattr = var.groupattr
  # groupdn - (optional) is a type of string
  groupdn = var.groupdn
  # groupfilter - (optional) is a type of string
  groupfilter = var.groupfilter
  # insecure_tls - (optional) is a type of bool
  insecure_tls = var.insecure_tls
  # path - (optional) is a type of string
  path = var.path
  # starttls - (optional) is a type of bool
  starttls = var.starttls
  # tls_max_version - (optional) is a type of string
  tls_max_version = var.tls_max_version
  # tls_min_version - (optional) is a type of string
  tls_min_version = var.tls_min_version
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
  # upndomain - (optional) is a type of string
  upndomain = var.upndomain
  # url - (required) is a type of string
  url = var.url
  # use_token_groups - (optional) is a type of bool
  use_token_groups = var.use_token_groups
  # userattr - (optional) is a type of string
  userattr = var.userattr
  # userdn - (optional) is a type of string
  userdn = var.userdn
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.accessor
}

output "binddn" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.binddn
}

output "bindpass" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.bindpass
  sensitive   = true
}

output "certificate" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.certificate
}

output "deny_null_bind" {
  description = "returns a bool"
  value       = vault_ldap_auth_backend.this.deny_null_bind
}

output "description" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.description
}

output "discoverdn" {
  description = "returns a bool"
  value       = vault_ldap_auth_backend.this.discoverdn
}

output "groupattr" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.groupattr
}

output "groupdn" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.groupdn
}

output "groupfilter" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.groupfilter
}

output "id" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.id
}

output "insecure_tls" {
  description = "returns a bool"
  value       = vault_ldap_auth_backend.this.insecure_tls
}

output "starttls" {
  description = "returns a bool"
  value       = vault_ldap_auth_backend.this.starttls
}

output "tls_max_version" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.tls_max_version
}

output "tls_min_version" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.tls_min_version
}

output "upndomain" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.upndomain
}

output "use_token_groups" {
  description = "returns a bool"
  value       = vault_ldap_auth_backend.this.use_token_groups
}

output "userattr" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.userattr
}

output "userdn" {
  description = "returns a string"
  value       = vault_ldap_auth_backend.this.userdn
}

output "this" {
  value = vault_ldap_auth_backend.this
}
```

[top](#index)