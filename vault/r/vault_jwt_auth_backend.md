# vault_jwt_auth_backend

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
module "vault_jwt_auth_backend" {
  source = "./modules/vault/r/vault_jwt_auth_backend"

  # bound_issuer - (optional) is a type of string
  bound_issuer = null
  # default_role - (optional) is a type of string
  default_role = null
  # description - (optional) is a type of string
  description = null
  # jwks_ca_pem - (optional) is a type of string
  jwks_ca_pem = null
  # jwks_url - (optional) is a type of string
  jwks_url = null
  # jwt_supported_algs - (optional) is a type of list of string
  jwt_supported_algs = []
  # jwt_validation_pubkeys - (optional) is a type of list of string
  jwt_validation_pubkeys = []
  # oidc_client_id - (optional) is a type of string
  oidc_client_id = null
  # oidc_client_secret - (optional) is a type of string
  oidc_client_secret = null
  # oidc_discovery_ca_pem - (optional) is a type of string
  oidc_discovery_ca_pem = null
  # oidc_discovery_url - (optional) is a type of string
  oidc_discovery_url = null
  # path - (optional) is a type of string
  path = null
  # provider_config - (optional) is a type of map of string
  provider_config = {}
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
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "bound_issuer" {
  description = "(optional) - The value against which to match the iss claim in a JWT"
  type        = string
  default     = null
}

variable "default_role" {
  description = "(optional) - The default role to use if none is provided during login"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - The description of the auth backend"
  type        = string
  default     = null
}

variable "jwks_ca_pem" {
  description = "(optional) - The CA certificate or chain of certificates, in PEM format, to use to validate connections to the JWKS URL. If not set, system certificates are used."
  type        = string
  default     = null
}

variable "jwks_url" {
  description = "(optional) - JWKS URL to use to authenticate signatures. Cannot be used with 'oidc_discovery_url' or 'jwt_validation_pubkeys'."
  type        = string
  default     = null
}

variable "jwt_supported_algs" {
  description = "(optional) - A list of supported signing algorithms. Defaults to [RS256]"
  type        = list(string)
  default     = null
}

variable "jwt_validation_pubkeys" {
  description = "(optional) - A list of PEM-encoded public keys to use to authenticate signatures locally. Cannot be used with 'jwks_url' or 'oidc_discovery_url'. "
  type        = list(string)
  default     = null
}

variable "oidc_client_id" {
  description = "(optional) - Client ID used for OIDC"
  type        = string
  default     = null
}

variable "oidc_client_secret" {
  description = "(optional) - Client Secret used for OIDC"
  type        = string
  default     = null
}

variable "oidc_discovery_ca_pem" {
  description = "(optional) - The CA certificate or chain of certificates, in PEM format, to use to validate connections to the OIDC Discovery URL. If not set, system certificates are used"
  type        = string
  default     = null
}

variable "oidc_discovery_url" {
  description = "(optional) - The OIDC Discovery URL, without any .well-known component (base path). Cannot be used with 'jwks_url' or 'jwt_validation_pubkeys'."
  type        = string
  default     = null
}

variable "path" {
  description = "(optional) - path to mount the backend"
  type        = string
  default     = null
}

variable "provider_config" {
  description = "(optional) - Provider specific handling configuration"
  type        = map(string)
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
  description = "(optional) - Type of backend. Can be either 'jwt' or 'oidc'"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_jwt_auth_backend" "this" {
  # bound_issuer - (optional) is a type of string
  bound_issuer = var.bound_issuer
  # default_role - (optional) is a type of string
  default_role = var.default_role
  # description - (optional) is a type of string
  description = var.description
  # jwks_ca_pem - (optional) is a type of string
  jwks_ca_pem = var.jwks_ca_pem
  # jwks_url - (optional) is a type of string
  jwks_url = var.jwks_url
  # jwt_supported_algs - (optional) is a type of list of string
  jwt_supported_algs = var.jwt_supported_algs
  # jwt_validation_pubkeys - (optional) is a type of list of string
  jwt_validation_pubkeys = var.jwt_validation_pubkeys
  # oidc_client_id - (optional) is a type of string
  oidc_client_id = var.oidc_client_id
  # oidc_client_secret - (optional) is a type of string
  oidc_client_secret = var.oidc_client_secret
  # oidc_discovery_ca_pem - (optional) is a type of string
  oidc_discovery_ca_pem = var.oidc_discovery_ca_pem
  # oidc_discovery_url - (optional) is a type of string
  oidc_discovery_url = var.oidc_discovery_url
  # path - (optional) is a type of string
  path = var.path
  # provider_config - (optional) is a type of map of string
  provider_config = var.provider_config
  # tune - (optional) is a type of set of object
  tune = var.tune
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_jwt_auth_backend.this.accessor
}

output "id" {
  description = "returns a string"
  value       = vault_jwt_auth_backend.this.id
}

output "tune" {
  description = "returns a set of object"
  value       = vault_jwt_auth_backend.this.tune
}

output "this" {
  value = vault_jwt_auth_backend.this
}
```

[top](#index)