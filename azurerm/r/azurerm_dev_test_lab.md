# azurerm_dev_test_lab

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_dev_test_lab" {
  source = "./modules/azurerm/r/azurerm_dev_test_lab"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "azurerm_dev_test_lab" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  storage_type        = var.storage_type
  tags                = var.tags

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
output "artifacts_storage_account_id" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.artifacts_storage_account_id
}

output "default_premium_storage_account_id" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.default_premium_storage_account_id
}

output "default_storage_account_id" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.default_storage_account_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.id
}

output "key_vault_id" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.key_vault_id
}

output "premium_data_disk_storage_account_id" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.premium_data_disk_storage_account_id
}

output "unique_identifier" {
  description = "returns a string"
  value       = azurerm_dev_test_lab.this.unique_identifier
}

output "this" {
  value = azurerm_dev_test_lab.this
}
```

[top](#index)