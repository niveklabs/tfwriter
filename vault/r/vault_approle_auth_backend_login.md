# vault_approle_auth_backend_login

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
module "vault_approle_auth_backend_login" {
  source = "./modules/vault/r/vault_approle_auth_backend_login"

  # backend - (optional) is a type of string
  backend = null
  # role_id - (required) is a type of string
  role_id = null
  # secret_id - (optional) is a type of string
  secret_id = null
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

variable "role_id" {
  description = "(required) - The RoleID to log in with."
  type        = string
}

variable "secret_id" {
  description = "(optional) - The SecretID to log in with."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_approle_auth_backend_login" "this" {
  backend   = var.backend
  role_id   = var.role_id
  secret_id = var.secret_id
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_approle_auth_backend_login.this.accessor
}

output "client_token" {
  description = "returns a string"
  value       = vault_approle_auth_backend_login.this.client_token
}

output "id" {
  description = "returns a string"
  value       = vault_approle_auth_backend_login.this.id
}

output "lease_duration" {
  description = "returns a number"
  value       = vault_approle_auth_backend_login.this.lease_duration
}

output "lease_started" {
  description = "returns a string"
  value       = vault_approle_auth_backend_login.this.lease_started
}

output "metadata" {
  description = "returns a map of string"
  value       = vault_approle_auth_backend_login.this.metadata
}

output "policies" {
  description = "returns a list of string"
  value       = vault_approle_auth_backend_login.this.policies
}

output "renewable" {
  description = "returns a bool"
  value       = vault_approle_auth_backend_login.this.renewable
}

output "this" {
  value = vault_approle_auth_backend_login.this
}
```

[top](#index)