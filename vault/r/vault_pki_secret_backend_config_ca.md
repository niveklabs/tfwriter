# vault_pki_secret_backend_config_ca

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
module "vault_pki_secret_backend_config_ca" {
  source = "./modules/vault/r/vault_pki_secret_backend_config_ca"

  # backend - (required) is a type of string
  backend = null
  # pem_bundle - (required) is a type of string
  pem_bundle = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The PKI secret backend the resource belongs to."
  type        = string
}

variable "pem_bundle" {
  description = "(required) - The key and certificate PEM bundle."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_config_ca" "this" {
  backend    = var.backend
  pem_bundle = var.pem_bundle
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_config_ca.this.id
}

output "this" {
  value = vault_pki_secret_backend_config_ca.this
}
```

[top](#index)