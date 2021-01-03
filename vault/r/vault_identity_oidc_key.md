# vault_identity_oidc_key

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
module "vault_identity_oidc_key" {
  source = "./modules/vault/r/vault_identity_oidc_key"

  # algorithm - (optional) is a type of string
  algorithm = null
  # allowed_client_ids - (optional) is a type of set of string
  allowed_client_ids = []
  # name - (required) is a type of string
  name = null
  # rotation_period - (optional) is a type of number
  rotation_period = null
  # verification_ttl - (optional) is a type of number
  verification_ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(optional) - Signing algorithm to use. Signing algorithm to use. Allowed values are: RS256 (default), RS384, RS512, ES256, ES384, ES512, EdDSA."
  type        = string
  default     = null
}

variable "allowed_client_ids" {
  description = "(optional) - Array of role client ids allowed to use this key for signing. If empty, no roles are allowed. If \"*\", all roles are allowed."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the key."
  type        = string
}

variable "rotation_period" {
  description = "(optional) - How often to generate a new signing key in number of seconds"
  type        = number
  default     = null
}

variable "verification_ttl" {
  description = "(optional) - Controls how long the public portion of a signing key will be available for verification after being rotated in seconds."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_oidc_key" "this" {
  algorithm          = var.algorithm
  allowed_client_ids = var.allowed_client_ids
  name               = var.name
  rotation_period    = var.rotation_period
  verification_ttl   = var.verification_ttl
}
```

[top](#index)

### Outputs

```terraform
output "allowed_client_ids" {
  description = "returns a set of string"
  value       = vault_identity_oidc_key.this.allowed_client_ids
}

output "id" {
  description = "returns a string"
  value       = vault_identity_oidc_key.this.id
}

output "this" {
  value = vault_identity_oidc_key.this
}
```

[top](#index)