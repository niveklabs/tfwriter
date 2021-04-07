# azurerm_monitor_diagnostic_setting

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
module "azurerm_monitor_diagnostic_setting" {
  source = "./modules/azurerm/r/azurerm_monitor_diagnostic_setting"

  # eventhub_authorization_rule_id - (optional) is a type of string
  eventhub_authorization_rule_id = null
  # eventhub_name - (optional) is a type of string
  eventhub_name = null
  # log_analytics_destination_type - (optional) is a type of string
  log_analytics_destination_type = null
  # log_analytics_workspace_id - (optional) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # storage_account_id - (optional) is a type of string
  storage_account_id = null
  # target_resource_id - (required) is a type of string
  target_resource_id = null

  log = [{
    category = null
    enabled  = null
    retention_policy = [{
      days    = null
      enabled = null
    }]
  }]

  metric = [{
    category = null
    enabled  = null
    retention_policy = [{
      days    = null
      enabled = null
    }]
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
variable "eventhub_authorization_rule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eventhub_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_analytics_destination_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_analytics_workspace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "storage_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_resource_id" {
  description = "(required)"
  type        = string
}

variable "log" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      enabled  = bool
      retention_policy = list(object(
        {
          days    = number
          enabled = bool
        }
      ))
    }
  ))
  default = []
}

variable "metric" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      enabled  = bool
      retention_policy = list(object(
        {
          days    = number
          enabled = bool
        }
      ))
    }
  ))
  default = []
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
resource "azurerm_monitor_diagnostic_setting" "this" {
  # eventhub_authorization_rule_id - (optional) is a type of string
  eventhub_authorization_rule_id = var.eventhub_authorization_rule_id
  # eventhub_name - (optional) is a type of string
  eventhub_name = var.eventhub_name
  # log_analytics_destination_type - (optional) is a type of string
  log_analytics_destination_type = var.log_analytics_destination_type
  # log_analytics_workspace_id - (optional) is a type of string
  log_analytics_workspace_id = var.log_analytics_workspace_id
  # name - (required) is a type of string
  name = var.name
  # storage_account_id - (optional) is a type of string
  storage_account_id = var.storage_account_id
  # target_resource_id - (required) is a type of string
  target_resource_id = var.target_resource_id

  dynamic "log" {
    for_each = var.log
    content {
      # category - (required) is a type of string
      category = log.value["category"]
      # enabled - (optional) is a type of bool
      enabled = log.value["enabled"]

      dynamic "retention_policy" {
        for_each = log.value.retention_policy
        content {
          # days - (optional) is a type of number
          days = retention_policy.value["days"]
          # enabled - (required) is a type of bool
          enabled = retention_policy.value["enabled"]
        }
      }

    }
  }

  dynamic "metric" {
    for_each = var.metric
    content {
      # category - (required) is a type of string
      category = metric.value["category"]
      # enabled - (optional) is a type of bool
      enabled = metric.value["enabled"]

      dynamic "retention_policy" {
        for_each = metric.value.retention_policy
        content {
          # days - (optional) is a type of number
          days = retention_policy.value["days"]
          # enabled - (required) is a type of bool
          enabled = retention_policy.value["enabled"]
        }
      }

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
  value       = azurerm_monitor_diagnostic_setting.this.id
}

output "this" {
  value = azurerm_monitor_diagnostic_setting.this
}
```

[top](#index)