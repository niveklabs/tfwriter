# azurerm_key_vault_secret

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_key_vault_secret" {
  source = "./modules/azurerm/d/azurerm_key_vault_secret"

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
data "azurerm_key_vault_secret" "this" {
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
output "content_type" {
  description = "returns a string"
  value       = data.azurerm_key_vault_secret.this.content_type
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_secret.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_key_vault_secret.this.tags
}

output "value" {
  description = "returns a string"
  value       = data.azurerm_key_vault_secret.this.value
  sensitive   = true
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_key_vault_secret.this.version
}

output "versionless_id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_secret.this.versionless_id
}

output "this" {
  value = azurerm_key_vault_secret.this
}
```

[top](#index)