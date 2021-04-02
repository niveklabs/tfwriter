# azurerm_storage_account_customer_managed_key

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_storage_account_customer_managed_key" {
  source = "./modules/azurerm/r/azurerm_storage_account_customer_managed_key"

  # key_name - (required) is a type of string
  key_name = null
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # key_version - (optional) is a type of string
  key_version = null
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
variable "key_name" {
  description = "(required)"
  type        = string
}

variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "key_version" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_storage_account_customer_managed_key" "this" {
  key_name           = var.key_name
  key_vault_id       = var.key_vault_id
  key_version        = var.key_version
  storage_account_id = var.storage_account_id

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
  value       = azurerm_storage_account_customer_managed_key.this.id
}

output "this" {
  value = azurerm_storage_account_customer_managed_key.this
}
```

[top](#index)