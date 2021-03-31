# vault_transform_alphabet

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
module "vault_transform_alphabet" {
  source = "./modules/vault/r/vault_transform_alphabet"

  # alphabet - (optional) is a type of string
  alphabet = null
  # name - (required) is a type of string
  name = null
  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "alphabet" {
  description = "(optional) - A string of characters that contains the alphabet set."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the alphabet."
  type        = string
}

variable "path" {
  description = "(required) - The mount path for a back-end, for example, the path given in \"$ vault auth enable -path=my-aws aws\"."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_transform_alphabet" "this" {
  alphabet = var.alphabet
  name     = var.name
  path     = var.path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_transform_alphabet.this.id
}

output "this" {
  value = vault_transform_alphabet.this
}
```

[top](#index)