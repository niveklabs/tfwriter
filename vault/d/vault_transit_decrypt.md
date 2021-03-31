# vault_transit_decrypt

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
module "vault_transit_decrypt" {
  source = "./modules/vault/d/vault_transit_decrypt"

  # backend - (required) is a type of string
  backend = null
  # ciphertext - (required) is a type of string
  ciphertext = null
  # context - (optional) is a type of string
  context = null
  # key - (required) is a type of string
  key = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The Transit secret backend the key belongs to."
  type        = string
}

variable "ciphertext" {
  description = "(required) - Transit encrypted cipher text."
  type        = string
}

variable "context" {
  description = "(optional) - Specifies the context for key derivation"
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - Name of the decryption key to use."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vault_transit_decrypt" "this" {
  backend    = var.backend
  ciphertext = var.ciphertext
  context    = var.context
  key        = var.key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vault_transit_decrypt.this.id
}

output "plaintext" {
  description = "returns a string"
  value       = data.vault_transit_decrypt.this.plaintext
  sensitive   = true
}

output "this" {
  value = vault_transit_decrypt.this
}
```

[top](#index)