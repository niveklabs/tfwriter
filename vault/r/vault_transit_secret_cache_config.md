# vault_transit_secret_cache_config

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
module "vault_transit_secret_cache_config" {
  source = "./modules/vault/r/vault_transit_secret_cache_config"

  # backend - (required) is a type of string
  backend = null
  # size - (required) is a type of number
  size = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The Transit secret backend the resource belongs to."
  type        = string
}

variable "size" {
  description = "(required) - Number of cache entries. A size of 0 mean unlimited."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "vault_transit_secret_cache_config" "this" {
  backend = var.backend
  size    = var.size
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_transit_secret_cache_config.this.id
}

output "this" {
  value = vault_transit_secret_cache_config.this
}
```

[top](#index)