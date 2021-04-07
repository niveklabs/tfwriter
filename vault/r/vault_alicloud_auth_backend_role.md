# vault_alicloud_auth_backend_role

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
module "vault_alicloud_auth_backend_role" {
  source = "./modules/vault/r/vault_alicloud_auth_backend_role"

  # arn - (required) is a type of string
  arn = null
  # backend - (optional) is a type of string
  backend = null
  # role - (required) is a type of string
  role = null
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
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required) - The role's arn."
  type        = string
}

variable "backend" {
  description = "(optional) - Auth backend."
  type        = string
  default     = null
}

variable "role" {
  description = "(required) - Name of the role. Must correspond with the name of the role reflected in the arn."
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "vault_alicloud_auth_backend_role" "this" {
  # arn - (required) is a type of string
  arn = var.arn
  # backend - (optional) is a type of string
  backend = var.backend
  # role - (required) is a type of string
  role = var.role
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
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_alicloud_auth_backend_role.this.id
}

output "this" {
  value = vault_alicloud_auth_backend_role.this
}
```

[top](#index)