# azurerm_cost_management_export_resource_group

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
module "azurerm_cost_management_export_resource_group" {
  source = "./modules/azurerm/r/azurerm_cost_management_export_resource_group"

  # active - (optional) is a type of bool
  active = null
  # name - (required) is a type of string
  name = null
  # recurrence_period_end - (required) is a type of string
  recurrence_period_end = null
  # recurrence_period_start - (required) is a type of string
  recurrence_period_start = null
  # recurrence_type - (required) is a type of string
  recurrence_type = null
  # resource_group_id - (required) is a type of string
  resource_group_id = null

  delivery_info = [{
    container_name     = null
    root_folder_path   = null
    storage_account_id = null
  }]

  query = [{
    time_frame = null
    type       = null
  }]

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
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "recurrence_period_end" {
  description = "(required)"
  type        = string
}

variable "recurrence_period_start" {
  description = "(required)"
  type        = string
}

variable "recurrence_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_id" {
  description = "(required)"
  type        = string
}

variable "delivery_info" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      container_name     = string
      root_folder_path   = string
      storage_account_id = string
    }
  ))
}

variable "query" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      time_frame = string
      type       = string
    }
  ))
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
resource "azurerm_cost_management_export_resource_group" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # name - (required) is a type of string
  name = var.name
  # recurrence_period_end - (required) is a type of string
  recurrence_period_end = var.recurrence_period_end
  # recurrence_period_start - (required) is a type of string
  recurrence_period_start = var.recurrence_period_start
  # recurrence_type - (required) is a type of string
  recurrence_type = var.recurrence_type
  # resource_group_id - (required) is a type of string
  resource_group_id = var.resource_group_id

  dynamic "delivery_info" {
    for_each = var.delivery_info
    content {
      # container_name - (required) is a type of string
      container_name = delivery_info.value["container_name"]
      # root_folder_path - (required) is a type of string
      root_folder_path = delivery_info.value["root_folder_path"]
      # storage_account_id - (required) is a type of string
      storage_account_id = delivery_info.value["storage_account_id"]
    }
  }

  dynamic "query" {
    for_each = var.query
    content {
      # time_frame - (required) is a type of string
      time_frame = query.value["time_frame"]
      # type - (required) is a type of string
      type = query.value["type"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azurerm_cost_management_export_resource_group.this.id
}

output "this" {
  value = azurerm_cost_management_export_resource_group.this
}
```

[top](#index)