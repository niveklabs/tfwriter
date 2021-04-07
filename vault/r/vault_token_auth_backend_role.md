# vault_token_auth_backend_role

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
module "vault_token_auth_backend_role" {
  source = "./modules/vault/r/vault_token_auth_backend_role"

  # allowed_policies - (optional) is a type of set of string
  allowed_policies = []
  # bound_cidrs - (optional) is a type of set of string
  bound_cidrs = []
  # disallowed_policies - (optional) is a type of set of string
  disallowed_policies = []
  # explicit_max_ttl - (optional) is a type of string
  explicit_max_ttl = null
  # orphan - (optional) is a type of bool
  orphan = null
  # path_suffix - (optional) is a type of string
  path_suffix = null
  # period - (optional) is a type of string
  period = null
  # renewable - (optional) is a type of bool
  renewable = null
  # role_name - (required) is a type of string
  role_name = null
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
variable "allowed_policies" {
  description = "(optional) - List of allowed policies for given role."
  type        = set(string)
  default     = null
}

variable "bound_cidrs" {
  description = "(optional) - List of CIDRs valid as the source address for login requests. This value is also encoded into any resulting token."
  type        = set(string)
  default     = null
}

variable "disallowed_policies" {
  description = "(optional) - List of disallowed policies for given role."
  type        = set(string)
  default     = null
}

variable "explicit_max_ttl" {
  description = "(optional) - Number of seconds after which issued tokens can no longer be renewed."
  type        = string
  default     = null
}

variable "orphan" {
  description = "(optional) - If true, tokens created against this policy will be orphan tokens."
  type        = bool
  default     = null
}

variable "path_suffix" {
  description = "(optional) - Tokens created against this role will have the given suffix as part of their path in addition to the role name."
  type        = string
  default     = null
}

variable "period" {
  description = "(optional) - Number of seconds to set the TTL to for issued tokens upon renewal. Makes the token a periodic token, which will never expire as long as it is renewed before the TTL each period."
  type        = string
  default     = null
}

variable "renewable" {
  description = "(optional) - Whether to disable the ability of the token to be renewed past its initial TTL."
  type        = bool
  default     = null
}

variable "role_name" {
  description = "(required) - Name of the role."
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
resource "vault_token_auth_backend_role" "this" {
  # allowed_policies - (optional) is a type of set of string
  allowed_policies = var.allowed_policies
  # bound_cidrs - (optional) is a type of set of string
  bound_cidrs = var.bound_cidrs
  # disallowed_policies - (optional) is a type of set of string
  disallowed_policies = var.disallowed_policies
  # explicit_max_ttl - (optional) is a type of string
  explicit_max_ttl = var.explicit_max_ttl
  # orphan - (optional) is a type of bool
  orphan = var.orphan
  # path_suffix - (optional) is a type of string
  path_suffix = var.path_suffix
  # period - (optional) is a type of string
  period = var.period
  # renewable - (optional) is a type of bool
  renewable = var.renewable
  # role_name - (required) is a type of string
  role_name = var.role_name
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
  value       = vault_token_auth_backend_role.this.id
}

output "this" {
  value = vault_token_auth_backend_role.this
}
```

[top](#index)