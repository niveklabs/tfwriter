# vault_identity_oidc

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
module "vault_identity_oidc" {
  source = "./modules/vault/r/vault_identity_oidc"

  # issuer - (optional) is a type of string
  issuer = null
}
```

[top](#index)

### Variables

```terraform
variable "issuer" {
  description = "(optional) - Issuer URL to be used in the iss claim of the token. If not set, Vault's api_addr will be used. The issuer is a case sensitive URL using the https scheme that contains scheme, host, and optionally, port number and path components, but no query or fragment components."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_oidc" "this" {
  issuer = var.issuer
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_identity_oidc.this.id
}

output "issuer" {
  description = "returns a string"
  value       = vault_identity_oidc.this.issuer
}

output "this" {
  value = vault_identity_oidc.this
}
```

[top](#index)