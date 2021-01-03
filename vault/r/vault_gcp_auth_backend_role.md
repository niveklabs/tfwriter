# vault_gcp_auth_backend_role

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
module "vault_gcp_auth_backend_role" {
  source = "./modules/vault/r/vault_gcp_auth_backend_role"

  # add_group_aliases - (optional) is a type of bool
  add_group_aliases = null
  # allow_gce_inference - (optional) is a type of bool
  allow_gce_inference = null
  # backend - (optional) is a type of string
  backend = null
  # bound_instance_groups - (optional) is a type of set of string
  bound_instance_groups = []
  # bound_labels - (optional) is a type of set of string
  bound_labels = []
  # bound_projects - (optional) is a type of set of string
  bound_projects = []
  # bound_regions - (optional) is a type of set of string
  bound_regions = []
  # bound_service_accounts - (optional) is a type of set of string
  bound_service_accounts = []
  # bound_zones - (optional) is a type of set of string
  bound_zones = []
  # max_jwt_exp - (optional) is a type of string
  max_jwt_exp = null
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # period - (optional) is a type of string
  period = null
  # policies - (optional) is a type of set of string
  policies = []
  # project_id - (optional) is a type of string
  project_id = null
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
  # ttl - (optional) is a type of string
  ttl = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "add_group_aliases" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_gce_inference" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "backend" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bound_instance_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "bound_labels" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "bound_projects" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "bound_regions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "bound_service_accounts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "bound_zones" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "max_jwt_exp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_gcp_auth_backend_role" "this" {
  add_group_aliases       = var.add_group_aliases
  allow_gce_inference     = var.allow_gce_inference
  backend                 = var.backend
  bound_instance_groups   = var.bound_instance_groups
  bound_labels            = var.bound_labels
  bound_projects          = var.bound_projects
  bound_regions           = var.bound_regions
  bound_service_accounts  = var.bound_service_accounts
  bound_zones             = var.bound_zones
  max_jwt_exp             = var.max_jwt_exp
  max_ttl                 = var.max_ttl
  period                  = var.period
  policies                = var.policies
  project_id              = var.project_id
  role                    = var.role
  token_bound_cidrs       = var.token_bound_cidrs
  token_explicit_max_ttl  = var.token_explicit_max_ttl
  token_max_ttl           = var.token_max_ttl
  token_no_default_policy = var.token_no_default_policy
  token_num_uses          = var.token_num_uses
  token_period            = var.token_period
  token_policies          = var.token_policies
  token_ttl               = var.token_ttl
  token_type              = var.token_type
  ttl                     = var.ttl
  type                    = var.type
}
```

[top](#index)

### Outputs

```terraform
output "add_group_aliases" {
  description = "returns a bool"
  value       = vault_gcp_auth_backend_role.this.add_group_aliases
}

output "allow_gce_inference" {
  description = "returns a bool"
  value       = vault_gcp_auth_backend_role.this.allow_gce_inference
}

output "bound_instance_groups" {
  description = "returns a set of string"
  value       = vault_gcp_auth_backend_role.this.bound_instance_groups
}

output "bound_labels" {
  description = "returns a set of string"
  value       = vault_gcp_auth_backend_role.this.bound_labels
}

output "bound_regions" {
  description = "returns a set of string"
  value       = vault_gcp_auth_backend_role.this.bound_regions
}

output "bound_service_accounts" {
  description = "returns a set of string"
  value       = vault_gcp_auth_backend_role.this.bound_service_accounts
}

output "bound_zones" {
  description = "returns a set of string"
  value       = vault_gcp_auth_backend_role.this.bound_zones
}

output "id" {
  description = "returns a string"
  value       = vault_gcp_auth_backend_role.this.id
}

output "max_jwt_exp" {
  description = "returns a string"
  value       = vault_gcp_auth_backend_role.this.max_jwt_exp
}

output "max_ttl" {
  description = "returns a string"
  value       = vault_gcp_auth_backend_role.this.max_ttl
}

output "period" {
  description = "returns a string"
  value       = vault_gcp_auth_backend_role.this.period
}

output "policies" {
  description = "returns a set of string"
  value       = vault_gcp_auth_backend_role.this.policies
}

output "ttl" {
  description = "returns a string"
  value       = vault_gcp_auth_backend_role.this.ttl
}

output "this" {
  value = vault_gcp_auth_backend_role.this
}
```

[top](#index)