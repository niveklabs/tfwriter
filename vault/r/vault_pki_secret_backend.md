# vault_pki_secret_backend

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
module "vault_pki_secret_backend" {
  source = "./modules/vault/r/vault_pki_secret_backend"

  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for tokens and secrets in seconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for tokens and secrets in seconds"
  type        = number
  default     = null
}

variable "path" {
  description = "(required) - Path to mount the backend at."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend" "this" {
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  # description - (optional) is a type of string
  description = var.description
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = var.max_lease_ttl_seconds
  # path - (required) is a type of string
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_pki_secret_backend.this.default_lease_ttl_seconds
}

output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend.this.id
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_pki_secret_backend.this.max_lease_ttl_seconds
}

output "this" {
  value = vault_pki_secret_backend.this
}
```

[top](#index)