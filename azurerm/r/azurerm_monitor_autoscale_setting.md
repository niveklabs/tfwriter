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
    azurerm = ">= 2.54.0"
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
        dimensions = [{
          name     = null
          operator = null
          values   = []
        }]
        metric_name        = null
        metric_namespace   = null
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
              dimensions = list(object(
                {
                  name     = string
                  operator = string
                  values   = list(string)
                }
              ))
              metric_name        = string
              metric_namespace   = string
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
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target_resource_id - (required) is a type of string
  target_resource_id = var.target_resource_id

  dynamic "notification" {
    for_each = var.notification
    content {

      dynamic "email" {
        for_each = notification.value.email
        content {
          # custom_emails - (optional) is a type of list of string
          custom_emails = email.value["custom_emails"]
          # send_to_subscription_administrator - (optional) is a type of bool
          send_to_subscription_administrator = email.value["send_to_subscription_administrator"]
          # send_to_subscription_co_administrator - (optional) is a type of bool
          send_to_subscription_co_administrator = email.value["send_to_subscription_co_administrator"]
        }
      }

      dynamic "webhook" {
        for_each = notification.value.webhook
        content {
          # properties - (optional) is a type of map of string
          properties = webhook.value["properties"]
          # service_uri - (required) is a type of string
          service_uri = webhook.value["service_uri"]
        }
      }

    }
  }

  dynamic "profile" {
    for_each = var.profile
    content {
      # name - (required) is a type of string
      name = profile.value["name"]

      dynamic "capacity" {
        for_each = profile.value.capacity
        content {
          # default - (required) is a type of number
          default = capacity.value["default"]
          # maximum - (required) is a type of number
          maximum = capacity.value["maximum"]
          # minimum - (required) is a type of number
          minimum = capacity.value["minimum"]
        }
      }

      dynamic "fixed_date" {
        for_each = profile.value.fixed_date
        content {
          # end - (required) is a type of string
          end = fixed_date.value["end"]
          # start - (required) is a type of string
          start = fixed_date.value["start"]
          # timezone - (optional) is a type of string
          timezone = fixed_date.value["timezone"]
        }
      }

      dynamic "recurrence" {
        for_each = profile.value.recurrence
        content {
          # days - (required) is a type of list of string
          days = recurrence.value["days"]
          # hours - (required) is a type of list of number
          hours = recurrence.value["hours"]
          # minutes - (required) is a type of list of number
          minutes = recurrence.value["minutes"]
          # timezone - (optional) is a type of string
          timezone = recurrence.value["timezone"]
        }
      }

      dynamic "rule" {
        for_each = profile.value.rule
        content {

          dynamic "metric_trigger" {
            for_each = rule.value.metric_trigger
            content {
              # metric_name - (required) is a type of string
              metric_name = metric_trigger.value["metric_name"]
              # metric_namespace - (optional) is a type of string
              metric_namespace = metric_trigger.value["metric_namespace"]
              # metric_resource_id - (required) is a type of string
              metric_resource_id = metric_trigger.value["metric_resource_id"]
              # operator - (required) is a type of string
              operator = metric_trigger.value["operator"]
              # statistic - (required) is a type of string
              statistic = metric_trigger.value["statistic"]
              # threshold - (required) is a type of number
              threshold = metric_trigger.value["threshold"]
              # time_aggregation - (required) is a type of string
              time_aggregation = metric_trigger.value["time_aggregation"]
              # time_grain - (required) is a type of string
              time_grain = metric_trigger.value["time_grain"]
              # time_window - (required) is a type of string
              time_window = metric_trigger.value["time_window"]

              dynamic "dimensions" {
                for_each = metric_trigger.value.dimensions
                content {
                  # name - (required) is a type of string
                  name = dimensions.value["name"]
                  # operator - (required) is a type of string
                  operator = dimensions.value["operator"]
                  # values - (required) is a type of list of string
                  values = dimensions.value["values"]
                }
              }

            }
          }

          dynamic "scale_action" {
            for_each = rule.value.scale_action
            content {
              # cooldown - (required) is a type of string
              cooldown = scale_action.value["cooldown"]
              # direction - (required) is a type of string
              direction = scale_action.value["direction"]
              # type - (required) is a type of string
              type = scale_action.value["type"]
              # value - (required) is a type of number
              value = scale_action.value["value"]
            }
          }

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
  value       = azurerm_monitor_autoscale_setting.this.id
}

output "this" {
  value = azurerm_monitor_autoscale_setting.this
}
```

[top](#index)