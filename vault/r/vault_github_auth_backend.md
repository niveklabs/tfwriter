# vault_github_auth_backend

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
module "vault_github_auth_backend" {
  source = "./modules/vault/r/vault_github_auth_backend"

  # base_url - (optional) is a type of string
  base_url = null
  # description - (optional) is a type of string
  description = null
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # organization - (required) is a type of string
  organization = null
  # path - (optional) is a type of string
  path = null
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
  # tune - (optional) is a type of set of object
  tune = [{
    allowed_response_headers     = []
    audit_non_hmac_request_keys  = []
    audit_non_hmac_response_keys = []
    default_lease_ttl            = null
    listing_visibility           = null
    max_lease_ttl                = null
    passthrough_request_headers  = []
    token_type                   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_url" {
  description = "(optional) - The API endpoint to use. Useful if you are running GitHub Enterprise or an API-compatible authentication server."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Specifies the description of the mount. This overrides the current stored value, if any."
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional) - Maximum duration after which authentication will be expired, in seconds."
  type        = string
  default     = null
}

variable "organization" {
  description = "(required) - The organization users must be part of."
  type        = string
}

variable "path" {
  description = "(optional) - Path where the auth backend is mounted"
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

variable "ttl" {
  description = "(optional) - Duration after which authentication will be expired, in seconds."
  type        = string
  default     = null
}

variable "tune" {
  description = "(optional)"
  type = set(object(
    {
      allowed_response_headers     = list(string)
      audit_non_hmac_request_keys  = list(string)
      audit_non_hmac_response_keys = list(string)
      default_lease_ttl            = string
      listing_visibility           = string
      max_lease_ttl                = string
      passthrough_request_headers  = list(string)
      token_type                   = string
    }
  ))
  default = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_github_auth_backend" "this" {
  base_url                = var.base_url
  description             = var.description
  max_ttl                 = var.max_ttl
  organization            = var.organization
  path                    = var.path
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
  tune                    = var.tune
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_github_auth_backend.this.accessor
}

output "id" {
  description = "returns a string"
  value       = vault_github_auth_backend.this.id
}

output "tune" {
  description = "returns a set of object"
  value       = vault_github_auth_backend.this.tune
}

output "this" {
  value = vault_github_auth_backend.this
}
```

[top](#index)