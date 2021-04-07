# azurerm_log_analytics_datasource_windows_performance_counter

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
module "azurerm_log_analytics_datasource_windows_performance_counter" {
  source = "./modules/azurerm/r/azurerm_log_analytics_datasource_windows_performance_counter"

  # counter_name - (required) is a type of string
  counter_name = null
  # instance_name - (required) is a type of string
  instance_name = null
  # interval_seconds - (required) is a type of number
  interval_seconds = null
  # name - (required) is a type of string
  name = null
  # object_name - (required) is a type of string
  object_name = null
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
variable "counter_name" {
  description = "(required)"
  type        = string
}

variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "interval_seconds" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "object_name" {
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
resource "azurerm_log_analytics_datasource_windows_performance_counter" "this" {
  # counter_name - (required) is a type of string
  counter_name = var.counter_name
  # instance_name - (required) is a type of string
  instance_name = var.instance_name
  # interval_seconds - (required) is a type of number
  interval_seconds = var.interval_seconds
  # name - (required) is a type of string
  name = var.name
  # object_name - (required) is a type of string
  object_name = var.object_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # workspace_name - (required) is a type of string
  workspace_name = var.workspace_name

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
  value       = azurerm_log_analytics_datasource_windows_performance_counter.this.id
}

output "this" {
  value = azurerm_log_analytics_datasource_windows_performance_counter.this
}
```

[top](#index)