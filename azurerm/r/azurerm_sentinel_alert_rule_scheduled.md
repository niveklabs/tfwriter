# azurerm_sentinel_alert_rule_scheduled

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
module "azurerm_sentinel_alert_rule_scheduled" {
  source = "./modules/azurerm/r/azurerm_sentinel_alert_rule_scheduled"

  # alert_rule_template_guid - (optional) is a type of string
  alert_rule_template_guid = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # query_frequency - (optional) is a type of string
  query_frequency = null
  # query_period - (optional) is a type of string
  query_period = null
  # severity - (required) is a type of string
  severity = null
  # suppression_duration - (optional) is a type of string
  suppression_duration = null
  # suppression_enabled - (optional) is a type of bool
  suppression_enabled = null
  # tactics - (optional) is a type of set of string
  tactics = []
  # trigger_operator - (optional) is a type of string
  trigger_operator = null
  # trigger_threshold - (optional) is a type of number
  trigger_threshold = null

  event_grouping = [{
    aggregation_method = null
  }]

  incident_configuration = [{
    create_incident = null
    grouping = [{
      enabled                 = null
      entity_matching_method  = null
      group_by                = []
      lookback_duration       = null
      reopen_closed_incidents = null
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
variable "alert_rule_template_guid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_analytics_workspace_id" {
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

variable "query_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_period" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(required)"
  type        = string
}

variable "suppression_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suppression_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tactics" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "trigger_operator" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trigger_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "event_grouping" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aggregation_method = string
    }
  ))
  default = []
}

variable "incident_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      create_incident = bool
      grouping = list(object(
        {
          enabled                 = bool
          entity_matching_method  = string
          group_by                = set(string)
          lookback_duration       = string
          reopen_closed_incidents = bool
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
resource "azurerm_sentinel_alert_rule_scheduled" "this" {
  alert_rule_template_guid   = var.alert_rule_template_guid
  description                = var.description
  display_name               = var.display_name
  enabled                    = var.enabled
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name
  query                      = var.query
  query_frequency            = var.query_frequency
  query_period               = var.query_period
  severity                   = var.severity
  suppression_duration       = var.suppression_duration
  suppression_enabled        = var.suppression_enabled
  tactics                    = var.tactics
  trigger_operator           = var.trigger_operator
  trigger_threshold          = var.trigger_threshold

  dynamic "event_grouping" {
    for_each = var.event_grouping
    content {
      aggregation_method = event_grouping.value["aggregation_method"]
    }
  }

  dynamic "incident_configuration" {
    for_each = var.incident_configuration
    content {
      create_incident = incident_configuration.value["create_incident"]

      dynamic "grouping" {
        for_each = incident_configuration.value.grouping
        content {
          enabled                 = grouping.value["enabled"]
          entity_matching_method  = grouping.value["entity_matching_method"]
          group_by                = grouping.value["group_by"]
          lookback_duration       = grouping.value["lookback_duration"]
          reopen_closed_incidents = grouping.value["reopen_closed_incidents"]
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
  value       = azurerm_sentinel_alert_rule_scheduled.this.id
}

output "this" {
  value = azurerm_sentinel_alert_rule_scheduled.this
}
```

[top](#index)