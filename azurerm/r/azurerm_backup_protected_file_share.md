# azurerm_backup_protected_file_share

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
module "azurerm_backup_protected_file_share" {
  source = "./modules/azurerm/r/azurerm_backup_protected_file_share"

  # backup_policy_id - (required) is a type of string
  backup_policy_id = null
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_file_share_name - (required) is a type of string
  source_file_share_name = null
  # source_storage_account_id - (required) is a type of string
  source_storage_account_id = null

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
variable "backup_policy_id" {
  description = "(required)"
  type        = string
}

variable "recovery_vault_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_file_share_name" {
  description = "(required)"
  type        = string
}

variable "source_storage_account_id" {
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
resource "azurerm_backup_protected_file_share" "this" {
  backup_policy_id          = var.backup_policy_id
  recovery_vault_name       = var.recovery_vault_name
  resource_group_name       = var.resource_group_name
  source_file_share_name    = var.source_file_share_name
  source_storage_account_id = var.source_storage_account_id

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
  value       = azurerm_backup_protected_file_share.this.id
}

output "this" {
  value = azurerm_backup_protected_file_share.this
}
```

[top](#index)