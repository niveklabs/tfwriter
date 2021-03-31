# vault_azure_auth_backend_role

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
module "vault_azure_auth_backend_role" {
  source = "./modules/vault/r/vault_azure_auth_backend_role"

  # backend - (optional) is a type of string
  backend = null
  # bound_group_ids - (optional) is a type of list of string
  bound_group_ids = []
  # bound_locations - (optional) is a type of list of string
  bound_locations = []
  # bound_resource_groups - (optional) is a type of list of string
  bound_resource_groups = []
  # bound_scale_sets - (optional) is a type of list of string
  bound_scale_sets = []
  # bound_service_principal_ids - (optional) is a type of list of string
  bound_service_principal_ids = []
  # bound_subscription_ids - (optional) is a type of list of string
  bound_subscription_ids = []
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # period - (optional) is a type of number
  period = null
  # policies - (optional) is a type of list of string
  policies = []
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
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

variable "bound_group_ids" {
  description = "(optional) - The list of group ids that login is restricted to."
  type        = list(string)
  default     = null
}

variable "bound_locations" {
  description = "(optional) - The list of locations that login is restricted to."
  type        = list(string)
  default     = null
}

variable "bound_resource_groups" {
  description = "(optional) - The list of resource groups that login is restricted to."
  type        = list(string)
  default     = null
}

variable "bound_scale_sets" {
  description = "(optional) - The list of scale set names that the login is restricted to."
  type        = list(string)
  default     = null
}

variable "bound_service_principal_ids" {
  description = "(optional) - The list of Service Principal IDs that login is restricted to."
  type        = list(string)
  default     = null
}

variable "bound_subscription_ids" {
  description = "(optional) - The list of subscription IDs that login is restricted to."
  type        = list(string)
  default     = null
}

variable "max_ttl" {
  description = "(optional) - The maximum allowed lifetime of tokens issued using this role, provided as the number of seconds."
  type        = number
  default     = null
}

variable "period" {
  description = "(optional) - If set, indicates that the token generated using this role should never expire. The token should be renewed within the duration specified by this value. At each renewal, the token's TTL will be set to the value of this field. The maximum allowed lifetime of token issued using this role. Specified as a number of seconds."
  type        = number
  default     = null
}

variable "policies" {
  description = "(optional) - Policies to be set on tokens issued using this role."
  type        = list(string)
  default     = null
}

variable "role" {
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
  description = "(optional) - The TTL period of tokens issued using this role, provided as the number of seconds."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_azure_auth_backend_role" "this" {
  backend                     = var.backend
  bound_group_ids             = var.bound_group_ids
  bound_locations             = var.bound_locations
  bound_resource_groups       = var.bound_resource_groups
  bound_scale_sets            = var.bound_scale_sets
  bound_service_principal_ids = var.bound_service_principal_ids
  bound_subscription_ids      = var.bound_subscription_ids
  max_ttl                     = var.max_ttl
  period                      = var.period
  policies                    = var.policies
  role                        = var.role
  token_bound_cidrs           = var.token_bound_cidrs
  token_explicit_max_ttl      = var.token_explicit_max_ttl
  token_max_ttl               = var.token_max_ttl
  token_no_default_policy     = var.token_no_default_policy
  token_num_uses              = var.token_num_uses
  token_period                = var.token_period
  token_policies              = var.token_policies
  token_ttl                   = var.token_ttl
  token_type                  = var.token_type
  ttl                         = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_azure_auth_backend_role.this.id
}

output "this" {
  value = vault_azure_auth_backend_role.this
}
```

[top](#index)