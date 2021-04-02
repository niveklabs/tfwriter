# azurerm_log_analytics_datasource_windows_event

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
module "azurerm_log_analytics_datasource_windows_event" {
  source = "./modules/azurerm/r/azurerm_log_analytics_datasource_windows_event"

  # event_log_name - (required) is a type of string
  event_log_name = null
  # event_types - (required) is a type of set of string
  event_types = []
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # workspace_name - (required) is a type of string
  workspace_name = null

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
variable "event_log_name" {
  description = "(required)"
  type        = string
}

variable "event_types" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "workspace_name" {
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
resource "azurerm_log_analytics_datasource_windows_event" "this" {
  event_log_name      = var.event_log_name
  event_types         = var.event_types
  name                = var.name
  resource_group_name = var.resource_group_name
  workspace_name      = var.workspace_name

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
  value       = azurerm_log_analytics_datasource_windows_event.this.id
}

output "this" {
  value = azurerm_log_analytics_datasource_windows_event.this
}
```

[top](#index)