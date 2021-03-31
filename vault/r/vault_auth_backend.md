# vault_auth_backend

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
module "vault_auth_backend" {
  source = "./modules/vault/r/vault_auth_backend"

  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # listing_visibility - (optional) is a type of string
  listing_visibility = null
  # local - (optional) is a type of bool
  local = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # path - (optional) is a type of string
  path = null
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
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration in seconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The description of the auth backend"
  type        = string
  default     = null
}

variable "listing_visibility" {
  description = "(optional) - Specifies whether to show this mount in the UI-specific listing endpoint"
  type        = string
  default     = null
}

variable "local" {
  description = "(optional) - Specifies if the auth method is local only"
  type        = bool
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration in seconds"
  type        = number
  default     = null
}

variable "path" {
  description = "(optional) - path to mount the backend. This defaults to the type."
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

variable "type" {
  description = "(required) - Name of the auth backend"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_auth_backend" "this" {
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  description               = var.description
  listing_visibility        = var.listing_visibility
  local                     = var.local
  max_lease_ttl_seconds     = var.max_lease_ttl_seconds
  path                      = var.path
  tune                      = var.tune
  type                      = var.type
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_auth_backend.this.accessor
}

output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_auth_backend.this.default_lease_ttl_seconds
}

output "id" {
  description = "returns a string"
  value       = vault_auth_backend.this.id
}

output "listing_visibility" {
  description = "returns a string"
  value       = vault_auth_backend.this.listing_visibility
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_auth_backend.this.max_lease_ttl_seconds
}

output "path" {
  description = "returns a string"
  value       = vault_auth_backend.this.path
}

output "tune" {
  description = "returns a set of object"
  value       = vault_auth_backend.this.tune
}

output "this" {
  value = vault_auth_backend.this
}
```

[top](#index)