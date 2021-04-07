# azurerm_monitor_metric_alert

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
module "azurerm_monitor_metric_alert" {
  source = "./modules/azurerm/r/azurerm_monitor_metric_alert"

  # auto_mitigate - (optional) is a type of bool
  auto_mitigate = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # frequency - (optional) is a type of string
  frequency = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scopes - (required) is a type of set of string
  scopes = []
  # severity - (optional) is a type of number
  severity = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_resource_location - (optional) is a type of string
  target_resource_location = null
  # target_resource_type - (optional) is a type of string
  target_resource_type = null
  # window_size - (optional) is a type of string
  window_size = null

  action = [{
    action_group_id    = null
    webhook_properties = {}
  }]

  application_insights_web_test_location_availability_criteria = [{
    component_id          = null
    failed_location_count = null
    web_test_id           = null
  }]

  criteria = [{
    aggregation = null
    dimension = [{
      name     = null
      operator = null
      values   = []
    }]
    metric_name            = null
    metric_namespace       = null
    operator               = null
    skip_metric_validation = null
    threshold              = null
  }]

  dynamic_criteria = [{
    aggregation       = null
    alert_sensitivity = null
    dimension = [{
      name     = null
      operator = null
      values   = []
    }]
    evaluation_failure_count = null
    evaluation_total_count   = null
    ignore_data_before       = null
    metric_name              = null
    metric_namespace         = null
    operator                 = null
    skip_metric_validation   = null
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
variable "auto_mitigate" {
  description = "(optional)"
  type        = bool
  default     = null
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
  description = "(optional)"
  type        = string
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

variable "scopes" {
  description = "(required)"
  type        = set(string)
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

variable "target_resource_location" {
  description = "(optional) - The location of the target resource. Required when using subscription, resource group scope or multiple scopes."
  type        = string
  default     = null
}

variable "target_resource_type" {
  description = "(optional) - The resource type (e.g. Microsoft.Compute/virtualMachines) of the target resource. Required when using subscription, resource group scope or multiple scopes."
  type        = string
  default     = null
}

variable "window_size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_group_id    = string
      webhook_properties = map(string)
    }
  ))
  default = []
}

variable "application_insights_web_test_location_availability_criteria" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      component_id          = string
      failed_location_count = number
      web_test_id           = string
    }
  ))
  default = []
}

variable "criteria" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      aggregation = string
      dimension = list(object(
        {
          name     = string
          operator = string
          values   = list(string)
        }
      ))
      metric_name            = string
      metric_namespace       = string
      operator               = string
      skip_metric_validation = bool
      threshold              = number
    }
  ))
  default = []
}

variable "dynamic_criteria" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      aggregation       = string
      alert_sensitivity = string
      dimension = list(object(
        {
          name     = string
          operator = string
          values   = list(string)
        }
      ))
      evaluation_failure_count = number
      evaluation_total_count   = number
      ignore_data_before       = string
      metric_name              = string
      metric_namespace         = string
      operator                 = string
      skip_metric_validation   = bool
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
resource "azurerm_monitor_metric_alert" "this" {
  # auto_mitigate - (optional) is a type of bool
  auto_mitigate = var.auto_mitigate
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # frequency - (optional) is a type of string
  frequency = var.frequency
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # scopes - (required) is a type of set of string
  scopes = var.scopes
  # severity - (optional) is a type of number
  severity = var.severity
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target_resource_location - (optional) is a type of string
  target_resource_location = var.target_resource_location
  # target_resource_type - (optional) is a type of string
  target_resource_type = var.target_resource_type
  # window_size - (optional) is a type of string
  window_size = var.window_size

  dynamic "action" {
    for_each = var.action
    content {
      # action_group_id - (required) is a type of string
      action_group_id = action.value["action_group_id"]
      # webhook_properties - (optional) is a type of map of string
      webhook_properties = action.value["webhook_properties"]
    }
  }

  dynamic "application_insights_web_test_location_availability_criteria" {
    for_each = var.application_insights_web_test_location_availability_criteria
    content {
      # component_id - (required) is a type of string
      component_id = application_insights_web_test_location_availability_criteria.value["component_id"]
      # failed_location_count - (required) is a type of number
      failed_location_count = application_insights_web_test_location_availability_criteria.value["failed_location_count"]
      # web_test_id - (required) is a type of string
      web_test_id = application_insights_web_test_location_availability_criteria.value["web_test_id"]
    }
  }

  dynamic "criteria" {
    for_each = var.criteria
    content {
      # aggregation - (required) is a type of string
      aggregation = criteria.value["aggregation"]
      # metric_name - (required) is a type of string
      metric_name = criteria.value["metric_name"]
      # metric_namespace - (required) is a type of string
      metric_namespace = criteria.value["metric_namespace"]
      # operator - (required) is a type of string
      operator = criteria.value["operator"]
      # skip_metric_validation - (optional) is a type of bool
      skip_metric_validation = criteria.value["skip_metric_validation"]
      # threshold - (required) is a type of number
      threshold = criteria.value["threshold"]

      dynamic "dimension" {
        for_each = criteria.value.dimension
        content {
          # name - (required) is a type of string
          name = dimension.value["name"]
          # operator - (required) is a type of string
          operator = dimension.value["operator"]
          # values - (required) is a type of list of string
          values = dimension.value["values"]
        }
      }

    }
  }

  dynamic "dynamic_criteria" {
    for_each = var.dynamic_criteria
    content {
      # aggregation - (required) is a type of string
      aggregation = dynamic_criteria.value["aggregation"]
      # alert_sensitivity - (required) is a type of string
      alert_sensitivity = dynamic_criteria.value["alert_sensitivity"]
      # evaluation_failure_count - (optional) is a type of number
      evaluation_failure_count = dynamic_criteria.value["evaluation_failure_count"]
      # evaluation_total_count - (optional) is a type of number
      evaluation_total_count = dynamic_criteria.value["evaluation_total_count"]
      # ignore_data_before - (optional) is a type of string
      ignore_data_before = dynamic_criteria.value["ignore_data_before"]
      # metric_name - (required) is a type of string
      metric_name = dynamic_criteria.value["metric_name"]
      # metric_namespace - (required) is a type of string
      metric_namespace = dynamic_criteria.value["metric_namespace"]
      # operator - (required) is a type of string
      operator = dynamic_criteria.value["operator"]
      # skip_metric_validation - (optional) is a type of bool
      skip_metric_validation = dynamic_criteria.value["skip_metric_validation"]

      dynamic "dimension" {
        for_each = dynamic_criteria.value.dimension
        content {
          # name - (required) is a type of string
          name = dimension.value["name"]
          # operator - (required) is a type of string
          operator = dimension.value["operator"]
          # values - (required) is a type of list of string
          values = dimension.value["values"]
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
  value       = azurerm_monitor_metric_alert.this.id
}

output "target_resource_location" {
  description = "returns a string"
  value       = azurerm_monitor_metric_alert.this.target_resource_location
}

output "target_resource_type" {
  description = "returns a string"
  value       = azurerm_monitor_metric_alert.this.target_resource_type
}

output "this" {
  value = azurerm_monitor_metric_alert.this
}
```

[top](#index)