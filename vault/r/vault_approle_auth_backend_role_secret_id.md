# vault_approle_auth_backend_role_secret_id

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
module "vault_approle_auth_backend_role_secret_id" {
  source = "./modules/vault/r/vault_approle_auth_backend_role_secret_id"

  # backend - (optional) is a type of string
  backend = null
  # cidr_list - (optional) is a type of set of string
  cidr_list = []
  # metadata - (optional) is a type of string
  metadata = null
  # role_name - (required) is a type of string
  role_name = null
  # secret_id - (optional) is a type of string
  secret_id = null
  # wrapping_ttl - (optional) is a type of string
  wrapping_ttl = null
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

variable "cidr_list" {
  description = "(optional) - List of CIDR blocks that can log in using the SecretID."
  type        = set(string)
  default     = null
}

variable "metadata" {
  description = "(optional) - JSON-encoded secret data to write."
  type        = string
  default     = null
}

variable "role_name" {
  description = "(required) - Name of the role."
  type        = string
}

variable "secret_id" {
  description = "(optional) - The SecretID to be managed. If not specified, Vault auto-generates one."
  type        = string
  default     = null
}

variable "wrapping_ttl" {
  description = "(optional) - The TTL duration of the wrapped SecretID."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_approle_auth_backend_role_secret_id" "this" {
  backend      = var.backend
  cidr_list    = var.cidr_list
  metadata     = var.metadata
  role_name    = var.role_name
  secret_id    = var.secret_id
  wrapping_ttl = var.wrapping_ttl
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_approle_auth_backend_role_secret_id.this.accessor
}

output "id" {
  description = "returns a string"
  value       = vault_approle_auth_backend_role_secret_id.this.id
}

output "secret_id" {
  description = "returns a string"
  value       = vault_approle_auth_backend_role_secret_id.this.secret_id
  sensitive   = true
}

output "wrapping_accessor" {
  description = "returns a string"
  value       = vault_approle_auth_backend_role_secret_id.this.wrapping_accessor
}

output "wrapping_token" {
  description = "returns a string"
  value       = vault_approle_auth_backend_role_secret_id.this.wrapping_token
  sensitive   = true
}

output "this" {
  value = vault_approle_auth_backend_role_secret_id.this
}
```

[top](#index)