# vault_pki_secret_backend_crl_config

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
module "vault_pki_secret_backend_crl_config" {
  source = "./modules/vault/r/vault_pki_secret_backend_crl_config"

  # backend - (required) is a type of string
  backend = null
  # disable - (optional) is a type of bool
  disable = null
  # expiry - (optional) is a type of string
  expiry = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The path of the PKI secret backend the resource belongs to."
  type        = string
}

variable "disable" {
  description = "(optional) - Disables or enables CRL building"
  type        = bool
  default     = null
}

variable "expiry" {
  description = "(optional) - Specifies the time until expiration."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_crl_config" "this" {
  backend = var.backend
  disable = var.disable
  expiry  = var.expiry
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_crl_config.this.id
}

output "this" {
  value = vault_pki_secret_backend_crl_config.this
}
```

[top](#index)