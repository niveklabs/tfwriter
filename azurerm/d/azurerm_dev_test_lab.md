# azurerm_dev_test_lab

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
module "azurerm_dev_test_lab" {
  source = "./modules/azurerm/d/azurerm_dev_test_lab"

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
data "azurerm_dev_test_lab" "this" {
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
output "artifacts_storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.artifacts_storage_account_id
}

output "default_premium_storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.default_premium_storage_account_id
}

output "default_storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.default_storage_account_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.id
}

output "key_vault_id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.key_vault_id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.location
}

output "premium_data_disk_storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.premium_data_disk_storage_account_id
}

output "storage_type" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.storage_type
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_dev_test_lab.this.tags
}

output "unique_identifier" {
  description = "returns a string"
  value       = data.azurerm_dev_test_lab.this.unique_identifier
}

output "this" {
  value = azurerm_dev_test_lab.this
}
```

[top](#index)