# vault_generic_secret

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
module "vault_generic_secret" {
  source = "./modules/vault/r/vault_generic_secret"

  # allow_read - (optional) is a type of bool
  allow_read = null
  # data_json - (required) is a type of string
  data_json = null
  # disable_read - (optional) is a type of bool
  disable_read = null
  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_read" {
  description = "(optional) - Attempt to read the token from Vault if true; if false, drift won't be detected."
  type        = bool
  default     = null
}

variable "data_json" {
  description = "(required) - JSON-encoded secret data to write."
  type        = string
}

variable "disable_read" {
  description = "(optional) - Don't attempt to read the token from Vault if true; drift won't be detected."
  type        = bool
  default     = null
}

variable "path" {
  description = "(required) - Full path where the generic secret will be written."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_generic_secret" "this" {
  # allow_read - (optional) is a type of bool
  allow_read = var.allow_read
  # data_json - (required) is a type of string
  data_json = var.data_json
  # disable_read - (optional) is a type of bool
  disable_read = var.disable_read
  # path - (required) is a type of string
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "data" {
  description = "returns a map of string"
  value       = vault_generic_secret.this.data
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = vault_generic_secret.this.id
}

output "this" {
  value = vault_generic_secret.this
}
```

[top](#index)