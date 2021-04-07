# vault_ssh_secret_backend_role

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
module "vault_ssh_secret_backend_role" {
  source = "./modules/vault/r/vault_ssh_secret_backend_role"

  # algorithm_signer - (optional) is a type of string
  algorithm_signer = null
  # allow_bare_domains - (optional) is a type of bool
  allow_bare_domains = null
  # allow_host_certificates - (optional) is a type of bool
  allow_host_certificates = null
  # allow_subdomains - (optional) is a type of bool
  allow_subdomains = null
  # allow_user_certificates - (optional) is a type of bool
  allow_user_certificates = null
  # allow_user_key_ids - (optional) is a type of bool
  allow_user_key_ids = null
  # allowed_critical_options - (optional) is a type of string
  allowed_critical_options = null
  # allowed_domains - (optional) is a type of string
  allowed_domains = null
  # allowed_extensions - (optional) is a type of string
  allowed_extensions = null
  # allowed_user_key_lengths - (optional) is a type of map of string
  allowed_user_key_lengths = {}
  # allowed_users - (optional) is a type of string
  allowed_users = null
  # allowed_users_template - (optional) is a type of bool
  allowed_users_template = null
  # backend - (required) is a type of string
  backend = null
  # cidr_list - (optional) is a type of string
  cidr_list = null
  # default_critical_options - (optional) is a type of map of string
  default_critical_options = {}
  # default_extensions - (optional) is a type of map of string
  default_extensions = {}
  # default_user - (optional) is a type of string
  default_user = null
  # key_id_format - (optional) is a type of string
  key_id_format = null
  # key_type - (required) is a type of string
  key_type = null
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # ttl - (optional) is a type of string
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "algorithm_signer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_bare_domains" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_host_certificates" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_subdomains" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_user_certificates" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_user_key_ids" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allowed_critical_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_domains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_extensions" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_user_key_lengths" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "allowed_users" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_users_template" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "backend" {
  description = "(required)"
  type        = string
}

variable "cidr_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_critical_options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "default_extensions" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "default_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_type" {
  description = "(required)"
  type        = string
}

variable "max_ttl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name for the role."
  type        = string
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
resource "vault_ssh_secret_backend_role" "this" {
  # algorithm_signer - (optional) is a type of string
  algorithm_signer = var.algorithm_signer
  # allow_bare_domains - (optional) is a type of bool
  allow_bare_domains = var.allow_bare_domains
  # allow_host_certificates - (optional) is a type of bool
  allow_host_certificates = var.allow_host_certificates
  # allow_subdomains - (optional) is a type of bool
  allow_subdomains = var.allow_subdomains
  # allow_user_certificates - (optional) is a type of bool
  allow_user_certificates = var.allow_user_certificates
  # allow_user_key_ids - (optional) is a type of bool
  allow_user_key_ids = var.allow_user_key_ids
  # allowed_critical_options - (optional) is a type of string
  allowed_critical_options = var.allowed_critical_options
  # allowed_domains - (optional) is a type of string
  allowed_domains = var.allowed_domains
  # allowed_extensions - (optional) is a type of string
  allowed_extensions = var.allowed_extensions
  # allowed_user_key_lengths - (optional) is a type of map of string
  allowed_user_key_lengths = var.allowed_user_key_lengths
  # allowed_users - (optional) is a type of string
  allowed_users = var.allowed_users
  # allowed_users_template - (optional) is a type of bool
  allowed_users_template = var.allowed_users_template
  # backend - (required) is a type of string
  backend = var.backend
  # cidr_list - (optional) is a type of string
  cidr_list = var.cidr_list
  # default_critical_options - (optional) is a type of map of string
  default_critical_options = var.default_critical_options
  # default_extensions - (optional) is a type of map of string
  default_extensions = var.default_extensions
  # default_user - (optional) is a type of string
  default_user = var.default_user
  # key_id_format - (optional) is a type of string
  key_id_format = var.key_id_format
  # key_type - (required) is a type of string
  key_type = var.key_type
  # max_ttl - (optional) is a type of string
  max_ttl = var.max_ttl
  # name - (required) is a type of string
  name = var.name
  # ttl - (optional) is a type of string
  ttl = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "algorithm_signer" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_role.this.algorithm_signer
}

output "id" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_role.this.id
}

output "max_ttl" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_role.this.max_ttl
}

output "ttl" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_role.this.ttl
}

output "this" {
  value = vault_ssh_secret_backend_role.this
}
```

[top](#index)