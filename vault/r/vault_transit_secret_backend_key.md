# vault_transit_secret_backend_key

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
module "vault_transit_secret_backend_key" {
  source = "./modules/vault/r/vault_transit_secret_backend_key"

  # allow_plaintext_backup - (optional) is a type of bool
  allow_plaintext_backup = null
  # backend - (required) is a type of string
  backend = null
  # convergent_encryption - (optional) is a type of bool
  convergent_encryption = null
  # deletion_allowed - (optional) is a type of bool
  deletion_allowed = null
  # derived - (optional) is a type of bool
  derived = null
  # exportable - (optional) is a type of bool
  exportable = null
  # min_decryption_version - (optional) is a type of number
  min_decryption_version = null
  # min_encryption_version - (optional) is a type of number
  min_encryption_version = null
  # name - (required) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_plaintext_backup" {
  description = "(optional) - If set, enables taking backup of named key in the plaintext format. Once set, this cannot be disabled."
  type        = bool
  default     = null
}

variable "backend" {
  description = "(required) - The Transit secret backend the resource belongs to."
  type        = string
}

variable "convergent_encryption" {
  description = "(optional) - Whether or not to support convergent encryption, where the same plaintext creates the same ciphertext. This requires derived to be set to true."
  type        = bool
  default     = null
}

variable "deletion_allowed" {
  description = "(optional) - Specifies if the key is allowed to be deleted."
  type        = bool
  default     = null
}

variable "derived" {
  description = "(optional) - Specifies if key derivation is to be used. If enabled, all encrypt/decrypt requests to this key must provide a context which is used for key derivation."
  type        = bool
  default     = null
}

variable "exportable" {
  description = "(optional) - Enables keys to be exportable. This allows for all the valid keys in the key ring to be exported. Once set, this cannot be disabled."
  type        = bool
  default     = null
}

variable "min_decryption_version" {
  description = "(optional) - Minimum key version to use for decryption."
  type        = number
  default     = null
}

variable "min_encryption_version" {
  description = "(optional) - Minimum key version to use for encryption"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the encryption key to create."
  type        = string
}

variable "type" {
  description = "(optional) - Specifies the type of key to create. The currently-supported types are: aes128-gcm96, aes256-gcm96, chacha20-poly1305, ed25519, ecdsa-p256, ecdsa-p384, ecdsa-p521, rsa-2048, rsa-3072, rsa-4096"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_transit_secret_backend_key" "this" {
  allow_plaintext_backup = var.allow_plaintext_backup
  backend                = var.backend
  convergent_encryption  = var.convergent_encryption
  deletion_allowed       = var.deletion_allowed
  derived                = var.derived
  exportable             = var.exportable
  min_decryption_version = var.min_decryption_version
  min_encryption_version = var.min_encryption_version
  name                   = var.name
  type                   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_transit_secret_backend_key.this.id
}

output "keys" {
  description = "returns a list of map of string"
  value       = vault_transit_secret_backend_key.this.keys
}

output "latest_version" {
  description = "returns a number"
  value       = vault_transit_secret_backend_key.this.latest_version
}

output "min_available_version" {
  description = "returns a number"
  value       = vault_transit_secret_backend_key.this.min_available_version
}

output "supports_decryption" {
  description = "returns a bool"
  value       = vault_transit_secret_backend_key.this.supports_decryption
}

output "supports_derivation" {
  description = "returns a bool"
  value       = vault_transit_secret_backend_key.this.supports_derivation
}

output "supports_encryption" {
  description = "returns a bool"
  value       = vault_transit_secret_backend_key.this.supports_encryption
}

output "supports_signing" {
  description = "returns a bool"
  value       = vault_transit_secret_backend_key.this.supports_signing
}

output "this" {
  value = vault_transit_secret_backend_key.this
}
```

[top](#index)