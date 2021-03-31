# vault_nomad_access_token

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
module "vault_nomad_access_token" {
  source = "./modules/vault/d/vault_nomad_access_token"

  # backend - (required) is a type of string
  backend = null
  # role - (required) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - Nomad secret backend to generate tokens from."
  type        = string
}

variable "role" {
  description = "(required) - Name of the role."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vault_nomad_access_token" "this" {
  backend = var.backend
  role    = var.role
}
```

[top](#index)

### Outputs

```terraform
output "accessor_id" {
  description = "returns a string"
  value       = data.vault_nomad_access_token.this.accessor_id
}

output "id" {
  description = "returns a string"
  value       = data.vault_nomad_access_token.this.id
}

output "secret_id" {
  description = "returns a string"
  value       = data.vault_nomad_access_token.this.secret_id
}

output "this" {
  value = vault_nomad_access_token.this
}
```

[top](#index)