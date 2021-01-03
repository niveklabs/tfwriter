# vault_namespace

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
module "vault_namespace" {
  source = "./modules/vault/r/vault_namespace"

  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "path" {
  description = "(required) - Path of the namespace."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_namespace" "this" {
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_namespace.this.id
}

output "namespace_id" {
  description = "returns a string"
  value       = vault_namespace.this.namespace_id
}

output "this" {
  value = vault_namespace.this
}
```

[top](#index)