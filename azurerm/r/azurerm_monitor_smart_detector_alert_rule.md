# azurerm_monitor_smart_detector_alert_rule

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
module "azurerm_monitor_smart_detector_alert_rule" {
  source = "./modules/azurerm/r/azurerm_monitor_smart_detector_alert_rule"

  # description - (optional) is a type of string
  description = null
  # detector_type - (required) is a type of string
  detector_type = null
  # enabled - (optional) is a type of bool
  enabled = null
  # frequency - (required) is a type of string
  frequency = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scope_resource_ids - (required) is a type of set of string
  scope_resource_ids = []
  # severity - (required) is a type of string
  severity = null
  # throttling_duration - (optional) is a type of string
  throttling_duration = null

  action_group = [{
    email_subject   = null
    ids             = []
    webhook_payload = null
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

variable "detector_type" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "frequency" {
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

variable "scope_resource_ids" {
  description = "(required)"
  type        = set(string)
}

variable "severity" {
  description = "(required)"
  type        = string
}

variable "throttling_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "action_group" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      email_subject   = string
      ids             = set(string)
      webhook_payload = string
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
resource "azurerm_monitor_smart_detector_alert_rule" "this" {
  description         = var.description
  detector_type       = var.detector_type
  enabled             = var.enabled
  frequency           = var.frequency
  name                = var.name
  resource_group_name = var.resource_group_name
  scope_resource_ids  = var.scope_resource_ids
  severity            = var.severity
  throttling_duration = var.throttling_duration

  dynamic "action_group" {
    for_each = var.action_group
    content {
      email_subject   = action_group.value["email_subject"]
      ids             = action_group.value["ids"]
      webhook_payload = action_group.value["webhook_payload"]
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
  value       = azurerm_monitor_smart_detector_alert_rule.this.id
}

output "this" {
  value = azurerm_monitor_smart_detector_alert_rule.this
}
```

[top](#index)