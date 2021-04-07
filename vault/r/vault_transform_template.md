# vault_transform_template

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
module "vault_transform_template" {
  source = "./modules/vault/r/vault_transform_template"

  # alphabet - (optional) is a type of string
  alphabet = null
  # name - (required) is a type of string
  name = null
  # path - (required) is a type of string
  path = null
  # pattern - (optional) is a type of string
  pattern = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "alphabet" {
  description = "(optional) - The alphabet to use for this template. This is only used during FPE transformations."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the template."
  type        = string
}

variable "path" {
  description = "(required) - The mount path for a back-end, for example, the path given in \"$ vault auth enable -path=my-aws aws\"."
  type        = string
}

variable "pattern" {
  description = "(optional) - The pattern used for matching. Currently, only regular expression pattern is supported."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - The pattern type to use for match detection. Currently, only regex is supported."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_transform_template" "this" {
  # alphabet - (optional) is a type of string
  alphabet = var.alphabet
  # name - (required) is a type of string
  name = var.name
  # path - (required) is a type of string
  path = var.path
  # pattern - (optional) is a type of string
  pattern = var.pattern
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_transform_template.this.id
}

output "this" {
  value = vault_transform_template.this
}
```

[top](#index)