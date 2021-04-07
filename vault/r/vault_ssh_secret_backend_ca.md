# vault_ssh_secret_backend_ca

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
module "vault_ssh_secret_backend_ca" {
  source = "./modules/vault/r/vault_ssh_secret_backend_ca"

  # backend - (optional) is a type of string
  backend = null
  # generate_signing_key - (optional) is a type of bool
  generate_signing_key = null
  # private_key - (optional) is a type of string
  private_key = null
  # public_key - (optional) is a type of string
  public_key = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - The path of the SSH Secret Backend where the CA should be configured"
  type        = string
  default     = null
}

variable "generate_signing_key" {
  description = "(optional) - Whether Vault should generate the signing key pair internally."
  type        = bool
  default     = null
}

variable "private_key" {
  description = "(optional) - Private key part the SSH CA key pair; required if generate_signing_key is false."
  type        = string
  default     = null
}

variable "public_key" {
  description = "(optional) - Public key part the SSH CA key pair; required if generate_signing_key is false."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_ssh_secret_backend_ca" "this" {
  # backend - (optional) is a type of string
  backend = var.backend
  # generate_signing_key - (optional) is a type of bool
  generate_signing_key = var.generate_signing_key
  # private_key - (optional) is a type of string
  private_key = var.private_key
  # public_key - (optional) is a type of string
  public_key = var.public_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_ca.this.id
}

output "private_key" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_ca.this.private_key
  sensitive   = true
}

output "public_key" {
  description = "returns a string"
  value       = vault_ssh_secret_backend_ca.this.public_key
}

output "this" {
  value = vault_ssh_secret_backend_ca.this
}
```

[top](#index)