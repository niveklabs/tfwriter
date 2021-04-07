# vault_auth_backend

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/vault/d/vault_auth_backend"

  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "path" {
  description = "(required) - The auth backend mount point."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vault_auth_backend" "this" {
  # path - (required) is a type of string
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = data.vault_auth_backend.this.accessor
}

output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = data.vault_auth_backend.this.default_lease_ttl_seconds
}

output "description" {
  description = "returns a string"
  value       = data.vault_auth_backend.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vault_auth_backend.this.id
}

output "listing_visibility" {
  description = "returns a string"
  value       = data.vault_auth_backend.this.listing_visibility
}

output "local" {
  description = "returns a bool"
  value       = data.vault_auth_backend.this.local
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = data.vault_auth_backend.this.max_lease_ttl_seconds
}

output "type" {
  description = "returns a string"
  value       = data.vault_auth_backend.this.type
}

output "this" {
  value = vault_auth_backend.this
}
```

[top](#index)