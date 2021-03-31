# vault_generic_secret

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
module "vault_generic_secret" {
  source = "./modules/vault/d/vault_generic_secret"

  # path - (required) is a type of string
  path = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "path" {
  description = "(required) - Full path from which a secret will be read."
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vault_generic_secret" "this" {
  path    = var.path
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "data" {
  description = "returns a map of string"
  value       = data.vault_generic_secret.this.data
  sensitive   = true
}

output "data_json" {
  description = "returns a string"
  value       = data.vault_generic_secret.this.data_json
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.vault_generic_secret.this.id
}

output "lease_duration" {
  description = "returns a number"
  value       = data.vault_generic_secret.this.lease_duration
}

output "lease_id" {
  description = "returns a string"
  value       = data.vault_generic_secret.this.lease_id
}

output "lease_renewable" {
  description = "returns a bool"
  value       = data.vault_generic_secret.this.lease_renewable
}

output "lease_start_time" {
  description = "returns a string"
  value       = data.vault_generic_secret.this.lease_start_time
}

output "this" {
  value = vault_generic_secret.this
}
```

[top](#index)