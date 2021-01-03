# azurerm_key_vault_key

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_key_vault_key" {
  source = "./modules/azurerm/d/azurerm_key_vault_key"

  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_key_vault_key" "this" {
  key_vault_id = var.key_vault_id
  name         = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "e" {
  description = "returns a string"
  value       = data.azurerm_key_vault_key.this.e
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_key.this.id
}

output "key_opts" {
  description = "returns a list of string"
  value       = data.azurerm_key_vault_key.this.key_opts
}

output "key_size" {
  description = "returns a number"
  value       = data.azurerm_key_vault_key.this.key_size
}

output "key_type" {
  description = "returns a string"
  value       = data.azurerm_key_vault_key.this.key_type
}

output "n" {
  description = "returns a string"
  value       = data.azurerm_key_vault_key.this.n
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_key_vault_key.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_key_vault_key.this.version
}

output "this" {
  value = azurerm_key_vault_key.this
}
```

[top](#index)