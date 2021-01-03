# azurerm_storage_encryption_scope

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
module "azurerm_storage_encryption_scope" {
  source = "./modules/azurerm/d/azurerm_storage_encryption_scope"

  # name - (required) is a type of string
  name = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "storage_account_id" {
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
data "azurerm_storage_encryption_scope" "this" {
  name               = var.name
  storage_account_id = var.storage_account_id

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_storage_encryption_scope.this.id
}

output "key_vault_key_id" {
  description = "returns a string"
  value       = data.azurerm_storage_encryption_scope.this.key_vault_key_id
}

output "source" {
  description = "returns a string"
  value       = data.azurerm_storage_encryption_scope.this.source
}

output "this" {
  value = azurerm_storage_encryption_scope.this
}
```

[top](#index)