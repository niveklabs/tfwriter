# azurerm_backup_container_storage_account

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "azurerm_backup_container_storage_account" {
  source = "./modules/azurerm/r/azurerm_backup_container_storage_account"

  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "recovery_vault_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_backup_container_storage_account" "this" {
  recovery_vault_name = var.recovery_vault_name
  resource_group_name = var.resource_group_name
  storage_account_id  = var.storage_account_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_backup_container_storage_account.this.id
}

output "this" {
  value = azurerm_backup_container_storage_account.this
}
```

[top](#index)