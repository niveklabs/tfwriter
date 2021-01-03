# azurerm_monitor_activity_log_alert

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
module "azurerm_monitor_activity_log_alert" {
  source = "./modules/azurerm/r/azurerm_monitor_activity_log_alert"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scopes - (required) is a type of set of string
  scopes = []
  # tags - (optional) is a type of map of string
  tags = {}

  action = [{
    action_group_id    = null
    webhook_properties = {}
  }]

  criteria = [{
    caller                  = null
    category                = null
    level                   = null
    operation_name          = null
    recommendation_category = null
    recommendation_impact   = null
    recommendation_type     = null
    resource_group          = null
    resource_id             = null
    resource_provider       = null
    resource_type           = null
    status                  = null
    sub_status              = null
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
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

variable "criteria" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      caller                  = string
      category                = string
      level                   = string
      operation_name          = string
      recommendation_category = string
      recommendation_impact   = string
      recommendation_type     = string
      resource_group          = string
      resource_id             = string
      resource_provider       = string
      resource_type           = string
      status                  = string
      sub_status              = string
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
resource "azurerm_monitor_activity_log_alert" "this" {
  description         = var.description
  enabled             = var.enabled
  name                = var.name
  resource_group_name = var.resource_group_name
  scopes              = var.scopes
  tags                = var.tags

  dynamic "action" {
    for_each = var.action
    content {
      action_group_id    = action.value["action_group_id"]
      webhook_properties = action.value["webhook_properties"]
    }
  }

  dynamic "criteria" {
    for_each = var.criteria
    content {
      caller                  = criteria.value["caller"]
      category                = criteria.value["category"]
      level                   = criteria.value["level"]
      operation_name          = criteria.value["operation_name"]
      recommendation_category = criteria.value["recommendation_category"]
      recommendation_impact   = criteria.value["recommendation_impact"]
      recommendation_type     = criteria.value["recommendation_type"]
      resource_group          = criteria.value["resource_group"]
      resource_id             = criteria.value["resource_id"]
      resource_provider       = criteria.value["resource_provider"]
      resource_type           = criteria.value["resource_type"]
      status                  = criteria.value["status"]
      sub_status              = criteria.value["sub_status"]
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
  value       = azurerm_monitor_activity_log_alert.this.id
}

output "this" {
  value = azurerm_monitor_activity_log_alert.this
}
```

[top](#index)