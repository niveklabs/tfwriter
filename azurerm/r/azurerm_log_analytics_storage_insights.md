# azurerm_log_analytics_storage_insights

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
module "azurerm_log_analytics_storage_insights" {
  source = "./modules/azurerm/r/azurerm_log_analytics_storage_insights"

  # blob_container_names - (optional) is a type of set of string
  blob_container_names = []
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null
  # storage_account_key - (required) is a type of string
  storage_account_key = null
  # table_names - (optional) is a type of set of string
  table_names = []
  # tags - (optional) is a type of map of string
  tags = {}
  # workspace_id - (required) is a type of string
  workspace_id = null

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
variable "blob_container_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
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

variable "storage_account_key" {
  description = "(required)"
  type        = string
}

variable "table_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "workspace_id" {
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
resource "azurerm_log_analytics_storage_insights" "this" {
  blob_container_names = var.blob_container_names
  name                 = var.name
  resource_group_name  = var.resource_group_name
  storage_account_id   = var.storage_account_id
  storage_account_key  = var.storage_account_key
  table_names          = var.table_names
  tags                 = var.tags
  workspace_id         = var.workspace_id

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
  value       = azurerm_log_analytics_storage_insights.this.id
}

output "this" {
  value = azurerm_log_analytics_storage_insights.this
}
```

[top](#index)