# vault_approle_auth_backend_role_id

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
module "vault_approle_auth_backend_role_id" {
  source = "./modules/vault/d/vault_approle_auth_backend_role_id"

  # backend - (optional) is a type of string
  backend = null
  # role_name - (required) is a type of string
  role_name = null
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

variable "role_name" {
  description = "(required) - Name of the role."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vault_approle_auth_backend_role_id" "this" {
  backend   = var.backend
  role_name = var.role_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vault_approle_auth_backend_role_id.this.id
}

output "role_id" {
  description = "returns a string"
  value       = data.vault_approle_auth_backend_role_id.this.role_id
}

output "this" {
  value = vault_approle_auth_backend_role_id.this
}
```

[top](#index)