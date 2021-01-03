# vault_kubernetes_auth_backend_role

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
module "vault_kubernetes_auth_backend_role" {
  source = "./modules/vault/r/vault_kubernetes_auth_backend_role"

  # audience - (optional) is a type of string
  audience = null
  # backend - (optional) is a type of string
  backend = null
  # bound_cidrs - (optional) is a type of set of string
  bound_cidrs = []
  # bound_service_account_names - (required) is a type of set of string
  bound_service_account_names = []
  # bound_service_account_namespaces - (required) is a type of set of string
  bound_service_account_namespaces = []
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # num_uses - (optional) is a type of number
  num_uses = null
  # period - (optional) is a type of number
  period = null
  # policies - (optional) is a type of set of string
  policies = []
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
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "audience" {
  description = "(optional) - Optional Audience claim to verify in the JWT."
  type        = string
  default     = null
}

variable "backend" {
  description = "(optional) - Unique name of the kubernetes backend to configure."
  type        = string
  default     = null
}

variable "bound_cidrs" {
  description = "(optional) - List of CIDRs valid as the source address for login requests. This value is also encoded into any resulting token."
  type        = set(string)
  default     = null
}

variable "bound_service_account_names" {
  description = "(required) - List of service account names able to access this role. If set to `[\"*\"]` all names are allowed, both this and bound_service_account_namespaces can not be \"*\"."
  type        = set(string)
}

variable "bound_service_account_namespaces" {
  description = "(required) - List of namespaces allowed to access this role. If set to `[\"*\"]` all namespaces are allowed, both this and bound_service_account_names can not be set to \"*\"."
  type        = set(string)
}

variable "max_ttl" {
  description = "(optional) - Number of seconds after which issued tokens can no longer be renewed."
  type        = number
  default     = null
}

variable "num_uses" {
  description = "(optional) - Number of times issued tokens can be used. Setting this to 0 or leaving it unset means unlimited uses."
  type        = number
  default     = null
}

variable "period" {
  description = "(optional) - Number of seconds to set the TTL to for issued tokens upon renewal. Makes the token a periodic token, which will never expire as long as it is renewed before the TTL each period."
  type        = number
  default     = null
}

variable "policies" {
  description = "(optional) - Policies to be set on tokens issued using this role."
  type        = set(string)
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

variable "ttl" {
  description = "(optional) - Default number of seconds to set as the TTL for issued tokens and at renewal time."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_kubernetes_auth_backend_role" "this" {
  audience                         = var.audience
  backend                          = var.backend
  bound_cidrs                      = var.bound_cidrs
  bound_service_account_names      = var.bound_service_account_names
  bound_service_account_namespaces = var.bound_service_account_namespaces
  max_ttl                          = var.max_ttl
  num_uses                         = var.num_uses
  period                           = var.period
  policies                         = var.policies
  role_name                        = var.role_name
  token_bound_cidrs                = var.token_bound_cidrs
  token_explicit_max_ttl           = var.token_explicit_max_ttl
  token_max_ttl                    = var.token_max_ttl
  token_no_default_policy          = var.token_no_default_policy
  token_num_uses                   = var.token_num_uses
  token_period                     = var.token_period
  token_policies                   = var.token_policies
  token_ttl                        = var.token_ttl
  token_type                       = var.token_type
  ttl                              = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_kubernetes_auth_backend_role.this.id
}

output "this" {
  value = vault_kubernetes_auth_backend_role.this
}
```

[top](#index)