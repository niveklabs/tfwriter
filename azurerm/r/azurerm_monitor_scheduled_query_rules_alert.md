# azurerm_monitor_scheduled_query_rules_alert

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
module "azurerm_monitor_scheduled_query_rules_alert" {
  source = "./modules/azurerm/r/azurerm_monitor_scheduled_query_rules_alert"

  # authorized_resource_ids - (optional) is a type of set of string
  authorized_resource_ids = []
  # data_source_id - (required) is a type of string
  data_source_id = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # frequency - (required) is a type of number
  frequency = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # query_type - (optional) is a type of string
  query_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # severity - (optional) is a type of number
  severity = null
  # tags - (optional) is a type of map of string
  tags = {}
  # throttling - (optional) is a type of number
  throttling = null
  # time_window - (required) is a type of number
  time_window = null

  action = [{
    action_group           = []
    custom_webhook_payload = null
    email_subject          = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  trigger = [{
    metric_trigger = [{
      metric_column       = null
      metric_trigger_type = null
      operator            = null
      threshold           = null
    }]
    operator  = null
    threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorized_resource_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "data_source_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "frequency" {
  description = "(required)"
  type        = number
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "query_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "severity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "throttling" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "time_window" {
  description = "(required)"
  type        = number
}

variable "action" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      action_group           = set(string)
      custom_webhook_payload = string
      email_subject          = string
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

variable "trigger" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      metric_trigger = list(object(
        {
          metric_column       = string
          metric_trigger_type = string
          operator            = string
          threshold           = number
        }
      ))
      operator  = string
      threshold = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_monitor_scheduled_query_rules_alert" "this" {
  authorized_resource_ids = var.authorized_resource_ids
  data_source_id          = var.data_source_id
  description             = var.description
  enabled                 = var.enabled
  frequency               = var.frequency
  location                = var.location
  name                    = var.name
  query                   = var.query
  query_type              = var.query_type
  resource_group_name     = var.resource_group_name
  severity                = var.severity
  tags                    = var.tags
  throttling              = var.throttling
  time_window             = var.time_window

  dynamic "action" {
    for_each = var.action
    content {
      action_group           = action.value["action_group"]
      custom_webhook_payload = action.value["custom_webhook_payload"]
      email_subject          = action.value["email_subject"]
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

  dynamic "trigger" {
    for_each = var.trigger
    content {
      operator  = trigger.value["operator"]
      threshold = trigger.value["threshold"]

      dynamic "metric_trigger" {
        for_each = trigger.value.metric_trigger
        content {
          metric_column       = metric_trigger.value["metric_column"]
          metric_trigger_type = metric_trigger.value["metric_trigger_type"]
          operator            = metric_trigger.value["operator"]
          threshold           = metric_trigger.value["threshold"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_monitor_scheduled_query_rules_alert.this.id
}

output "this" {
  value = azurerm_monitor_scheduled_query_rules_alert.this
}
```

[top](#index)