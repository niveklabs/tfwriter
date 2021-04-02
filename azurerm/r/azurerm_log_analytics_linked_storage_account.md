# azurerm_log_analytics_linked_storage_account

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
module "azurerm_log_analytics_linked_storage_account" {
  source = "./modules/azurerm/r/azurerm_log_analytics_linked_storage_account"

  # data_source_type - (required) is a type of string
  data_source_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_ids - (required) is a type of set of string
  storage_account_ids = []
  # workspace_resource_id - (required) is a type of string
  workspace_resource_id = null

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
variable "data_source_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_account_ids" {
  description = "(required)"
  type        = set(string)
}

variable "workspace_resource_id" {
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
resource "azurerm_log_analytics_linked_storage_account" "this" {
  data_source_type      = var.data_source_type
  resource_group_name   = var.resource_group_name
  storage_account_ids   = var.storage_account_ids
  workspace_resource_id = var.workspace_resource_id

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
  value       = azurerm_log_analytics_linked_storage_account.this.id
}

output "this" {
  value = azurerm_log_analytics_linked_storage_account.this
}
```

[top](#index)