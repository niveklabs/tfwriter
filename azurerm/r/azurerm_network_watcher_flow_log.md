# azurerm_network_watcher_flow_log

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
module "azurerm_network_watcher_flow_log" {
  source = "./modules/azurerm/r/azurerm_network_watcher_flow_log"

  # enabled - (required) is a type of bool
  enabled = null
  # network_security_group_id - (required) is a type of string
  network_security_group_id = null
  # network_watcher_name - (required) is a type of string
  network_watcher_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null
  # version - (optional) is a type of number
  version = null

  retention_policy = [{
    days    = null
    enabled = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  traffic_analytics = [{
    enabled               = null
    interval_in_minutes   = null
    workspace_id          = null
    workspace_region      = null
    workspace_resource_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "network_security_group_id" {
  description = "(required)"
  type        = string
}

variable "network_watcher_name" {
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

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retention_policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      days    = number
      enabled = bool
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

variable "traffic_analytics" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled               = bool
      interval_in_minutes   = number
      workspace_id          = string
      workspace_region      = string
      workspace_resource_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_network_watcher_flow_log" "this" {
  enabled                   = var.enabled
  network_security_group_id = var.network_security_group_id
  network_watcher_name      = var.network_watcher_name
  resource_group_name       = var.resource_group_name
  storage_account_id        = var.storage_account_id
  version                   = var.version

  dynamic "retention_policy" {
    for_each = var.retention_policy
    content {
      days    = retention_policy.value["days"]
      enabled = retention_policy.value["enabled"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

  dynamic "traffic_analytics" {
    for_each = var.traffic_analytics
    content {
      enabled               = traffic_analytics.value["enabled"]
      interval_in_minutes   = traffic_analytics.value["interval_in_minutes"]
      workspace_id          = traffic_analytics.value["workspace_id"]
      workspace_region      = traffic_analytics.value["workspace_region"]
      workspace_resource_id = traffic_analytics.value["workspace_resource_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_network_watcher_flow_log.this.id
}

output "version" {
  description = "returns a number"
  value       = azurerm_network_watcher_flow_log.this.version
}

output "this" {
  value = azurerm_network_watcher_flow_log.this
}
```

[top](#index)