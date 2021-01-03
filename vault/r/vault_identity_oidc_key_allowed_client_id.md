# vault_identity_oidc_key_allowed_client_id

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
module "vault_identity_oidc_key_allowed_client_id" {
  source = "./modules/vault/r/vault_identity_oidc_key_allowed_client_id"

  # allowed_client_id - (required) is a type of string
  allowed_client_id = null
  # key_name - (required) is a type of string
  key_name = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_client_id" {
  description = "(required) - Role Client ID allowed to use the key for signing."
  type        = string
}

variable "key_name" {
  description = "(required) - Name of the key."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_oidc_key_allowed_client_id" "this" {
  allowed_client_id = var.allowed_client_id
  key_name          = var.key_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_identity_oidc_key_allowed_client_id.this.id
}

output "this" {
  value = vault_identity_oidc_key_allowed_client_id.this
}
```

[top](#index)