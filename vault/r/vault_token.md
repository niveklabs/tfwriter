# vault_token

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
module "vault_token" {
  source = "./modules/vault/r/vault_token"

  # display_name - (optional) is a type of string
  display_name = null
  # explicit_max_ttl - (optional) is a type of string
  explicit_max_ttl = null
  # no_default_policy - (optional) is a type of bool
  no_default_policy = null
  # no_parent - (optional) is a type of bool
  no_parent = null
  # num_uses - (optional) is a type of number
  num_uses = null
  # period - (optional) is a type of string
  period = null
  # pgp_key - (optional) is a type of string
  pgp_key = null
  # policies - (optional) is a type of set of string
  policies = []
  # renew_increment - (optional) is a type of number
  renew_increment = null
  # renew_min_lease - (optional) is a type of number
  renew_min_lease = null
  # renewable - (optional) is a type of bool
  renewable = null
  # role_name - (optional) is a type of string
  role_name = null
  # ttl - (optional) is a type of string
  ttl = null
  # wrapping_ttl - (optional) is a type of string
  wrapping_ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional) - The display name of the token."
  type        = string
  default     = null
}

variable "explicit_max_ttl" {
  description = "(optional) - The explicit max TTL of the token."
  type        = string
  default     = null
}

variable "no_default_policy" {
  description = "(optional) - Flag to disable the default policy."
  type        = bool
  default     = null
}

variable "no_parent" {
  description = "(optional) - Flag to create a token without parent."
  type        = bool
  default     = null
}

variable "num_uses" {
  description = "(optional) - The number of allowed uses of the token."
  type        = number
  default     = null
}

variable "period" {
  description = "(optional) - The period of the token."
  type        = string
  default     = null
}

variable "pgp_key" {
  description = "(optional) - The PGP key (base64 encoded) to encrypt the token."
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - List of policies."
  type        = set(string)
  default     = null
}

variable "renew_increment" {
  description = "(optional) - The renew increment."
  type        = number
  default     = null
}

variable "renew_min_lease" {
  description = "(optional) - The minimum lease to renew token."
  type        = number
  default     = null
}

variable "renewable" {
  description = "(optional) - Flag to allow the token to be renewed"
  type        = bool
  default     = null
}

variable "role_name" {
  description = "(optional) - The token role name."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - The TTL period of the token."
  type        = string
  default     = null
}

variable "wrapping_ttl" {
  description = "(optional) - The TTL period of the wrapped token."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_token" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # explicit_max_ttl - (optional) is a type of string
  explicit_max_ttl = var.explicit_max_ttl
  # no_default_policy - (optional) is a type of bool
  no_default_policy = var.no_default_policy
  # no_parent - (optional) is a type of bool
  no_parent = var.no_parent
  # num_uses - (optional) is a type of number
  num_uses = var.num_uses
  # period - (optional) is a type of string
  period = var.period
  # pgp_key - (optional) is a type of string
  pgp_key = var.pgp_key
  # policies - (optional) is a type of set of string
  policies = var.policies
  # renew_increment - (optional) is a type of number
  renew_increment = var.renew_increment
  # renew_min_lease - (optional) is a type of number
  renew_min_lease = var.renew_min_lease
  # renewable - (optional) is a type of bool
  renewable = var.renewable
  # role_name - (optional) is a type of string
  role_name = var.role_name
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # wrapping_ttl - (optional) is a type of string
  wrapping_ttl = var.wrapping_ttl
}
```

[top](#index)

### Outputs

```terraform
output "client_token" {
  description = "returns a string"
  value       = vault_token.this.client_token
  sensitive   = true
}

output "encrypted_client_token" {
  description = "returns a string"
  value       = vault_token.this.encrypted_client_token
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = vault_token.this.id
}

output "lease_duration" {
  description = "returns a number"
  value       = vault_token.this.lease_duration
}

output "lease_started" {
  description = "returns a string"
  value       = vault_token.this.lease_started
}

output "no_parent" {
  description = "returns a bool"
  value       = vault_token.this.no_parent
}

output "num_uses" {
  description = "returns a number"
  value       = vault_token.this.num_uses
}

output "renewable" {
  description = "returns a bool"
  value       = vault_token.this.renewable
}

output "wrapped_token" {
  description = "returns a string"
  value       = vault_token.this.wrapped_token
  sensitive   = true
}

output "wrapping_accessor" {
  description = "returns a string"
  value       = vault_token.this.wrapping_accessor
  sensitive   = true
}

output "this" {
  value = vault_token.this
}
```

[top](#index)