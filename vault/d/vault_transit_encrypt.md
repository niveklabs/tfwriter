# vault_transit_encrypt

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
module "vault_transit_encrypt" {
  source = "./modules/vault/d/vault_transit_encrypt"

  # backend - (required) is a type of string
  backend = null
  # context - (optional) is a type of string
  context = null
  # key - (required) is a type of string
  key = null
  # key_version - (optional) is a type of number
  key_version = null
  # plaintext - (required) is a type of string
  plaintext = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The Transit secret backend the key belongs to."
  type        = string
}

variable "context" {
  description = "(optional) - Specifies the context for key derivation"
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - Name of the encryption key to use."
  type        = string
}

variable "key_version" {
  description = "(optional) - The version of the key to use for encryption"
  type        = number
  default     = null
}

variable "plaintext" {
  description = "(required) - Map of strings read from Vault."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vault_transit_encrypt" "this" {
  backend     = var.backend
  context     = var.context
  key         = var.key
  key_version = var.key_version
  plaintext   = var.plaintext
}
```

[top](#index)

### Outputs

```terraform
output "ciphertext" {
  description = "returns a string"
  value       = data.vault_transit_encrypt.this.ciphertext
}

output "id" {
  description = "returns a string"
  value       = data.vault_transit_encrypt.this.id
}

output "this" {
  value = vault_transit_encrypt.this
}
```

[top](#index)