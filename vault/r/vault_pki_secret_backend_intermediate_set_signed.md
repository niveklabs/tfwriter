# vault_pki_secret_backend_intermediate_set_signed

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
module "vault_pki_secret_backend_intermediate_set_signed" {
  source = "./modules/vault/r/vault_pki_secret_backend_intermediate_set_signed"

  # backend - (required) is a type of string
  backend = null
  # certificate - (required) is a type of string
  certificate = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The PKI secret backend the resource belongs to."
  type        = string
}

variable "certificate" {
  description = "(required) - The certificate."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_intermediate_set_signed" "this" {
  backend     = var.backend
  certificate = var.certificate
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_intermediate_set_signed.this.id
}

output "this" {
  value = vault_pki_secret_backend_intermediate_set_signed.this
}
```

[top](#index)