# azurerm_batch_account

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_batch_account" {
  source = "./modules/azurerm/d/azurerm_batch_account"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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

variable "resource_group_name" {
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
data "azurerm_batch_account" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "account_endpoint" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.account_endpoint
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.id
}

output "key_vault_reference" {
  description = "returns a list of object"
  value       = data.azurerm_batch_account.this.key_vault_reference
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.location
}

output "pool_allocation_mode" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.pool_allocation_mode
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.primary_access_key
  sensitive   = true
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.secondary_access_key
  sensitive   = true
}

output "storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_batch_account.this.storage_account_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_batch_account.this.tags
}

output "this" {
  value = azurerm_batch_account.this
}
```

[top](#index)