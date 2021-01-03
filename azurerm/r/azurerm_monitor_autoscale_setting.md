# azurerm_monitor_autoscale_setting

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
module "azurerm_monitor_autoscale_setting" {
  source = "./modules/azurerm/r/azurerm_monitor_autoscale_setting"

  # enabled - (optional) is a type of bool
  enabled = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_resource_id - (required) is a type of string
  target_resource_id = null

  notification = [{
    email = [{
      custom_emails                         = []
      send_to_subscription_administrator    = null
      send_to_subscription_co_administrator = null
    }]
    webhook = [{
      properties  = {}
      service_uri = null
    }]
  }]

  profile = [{
    capacity = [{
      default = null
      maximum = null
      minimum = null
    }]
    fixed_date = [{
      end      = null
      start    = null
      timezone = null
    }]
    name = null
    recurrence = [{
      days     = []
      hours    = []
      minutes  = []
      timezone = null
    }]
    rule = [{
      metric_trigger = [{
        metric_name        = null
        metric_resource_id = null
        operator           = null
        statistic          = null
        threshold          = null
        time_aggregation   = null
        time_grain         = null
        time_window        = null
      }]
      scale_action = [{
        cooldown  = null
        direction = null
        type      = null
        value     = null
      }]
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
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_resource_id" {
  description = "(required)"
  type        = string
}

variable "notification" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      email = list(object(
        {
          custom_emails                         = list(string)
          send_to_subscription_administrator    = bool
          send_to_subscription_co_administrator = bool
        }
      ))
      webhook = list(object(
        {
          properties  = map(string)
          service_uri = string
        }
      ))
    }
  ))
  default = []
}

variable "profile" {
  description = "nested block: NestingList, min items: 1, max items: 20"
  type = set(object(
    {
      capacity = list(object(
        {
          default = number
          maximum = number
          minimum = number
        }
      ))
      fixed_date = list(object(
        {
          end      = string
          start    = string
          timezone = string
        }
      ))
      name = string
      recurrence = list(object(
        {
          days     = list(string)
          hours    = list(number)
          minutes  = list(number)
          timezone = string
        }
      ))
      rule = list(object(
        {
          metric_trigger = list(object(
            {
              metric_name        = string
              metric_resource_id = string
              operator           = string
              statistic          = string
              threshold          = number
              time_aggregation   = string
              time_grain         = string
              time_window        = string
            }
          ))
          scale_action = list(object(
            {
              cooldown  = string
              direction = string
              type      = string
              value     = number
            }
          ))
        }
      ))
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
resource "azurerm_monitor_autoscale_setting" "this" {
  enabled             = var.enabled
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags
  target_resource_id  = var.target_resource_id

  dynamic "notification" {
    for_each = var.notification
    content {

      dynamic "email" {
        for_each = notification.value.email
        content {
          custom_emails                         = email.value["custom_emails"]
          send_to_subscription_administrator    = email.value["send_to_subscription_administrator"]
          send_to_subscription_co_administrator = email.value["send_to_subscription_co_administrator"]
        }
      }

      dynamic "webhook" {
        for_each = notification.value.webhook
        content {
          properties  = webhook.value["properties"]
          service_uri = webhook.value["service_uri"]
        }
      }

    }
  }

  dynamic "profile" {
    for_each = var.profile
    content {
      name = profile.value["name"]

      dynamic "capacity" {
        for_each = profile.value.capacity
        content {
          default = capacity.value["default"]
          maximum = capacity.value["maximum"]
          minimum = capacity.value["minimum"]
        }
      }

      dynamic "fixed_date" {
        for_each = profile.value.fixed_date
        content {
          end      = fixed_date.value["end"]
          start    = fixed_date.value["start"]
          timezone = fixed_date.value["timezone"]
        }
      }

      dynamic "recurrence" {
        for_each = profile.value.recurrence
        content {
          days     = recurrence.value["days"]
          hours    = recurrence.value["hours"]
          minutes  = recurrence.value["minutes"]
          timezone = recurrence.value["timezone"]
        }
      }

      dynamic "rule" {
        for_each = profile.value.rule
        content {

          dynamic "metric_trigger" {
            for_each = rule.value.metric_trigger
            content {
              metric_name        = metric_trigger.value["metric_name"]
              metric_resource_id = metric_trigger.value["metric_resource_id"]
              operator           = metric_trigger.value["operator"]
              statistic          = metric_trigger.value["statistic"]
              threshold          = metric_trigger.value["threshold"]
              time_aggregation   = metric_trigger.value["time_aggregation"]
              time_grain         = metric_trigger.value["time_grain"]
              time_window        = metric_trigger.value["time_window"]
            }
          }

          dynamic "scale_action" {
            for_each = rule.value.scale_action
            content {
              cooldown  = scale_action.value["cooldown"]
              direction = scale_action.value["direction"]
              type      = scale_action.value["type"]
              value     = scale_action.value["value"]
            }
          }

        }
      }

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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_monitor_autoscale_setting.this.id
}

output "this" {
  value = azurerm_monitor_autoscale_setting.this
}
```

[top](#index)