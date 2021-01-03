# azurerm_monitor_action_group

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_monitor_action_group" {
  source = "./modules/azurerm/d/azurerm_monitor_action_group"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_monitor_action_group" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arm_role_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.arm_role_receiver
}

output "automation_runbook_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.automation_runbook_receiver
}

output "azure_app_push_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.azure_app_push_receiver
}

output "azure_function_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.azure_function_receiver
}

output "email_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.email_receiver
}

output "enabled" {
  description = "returns a bool"
  value       = data.azurerm_monitor_action_group.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_monitor_action_group.this.id
}

output "itsm_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.itsm_receiver
}

output "logic_app_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.logic_app_receiver
}

output "short_name" {
  description = "returns a string"
  value       = data.azurerm_monitor_action_group.this.short_name
}

output "sms_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.sms_receiver
}

output "voice_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.voice_receiver
}

output "webhook_receiver" {
  description = "returns a list of object"
  value       = data.azurerm_monitor_action_group.this.webhook_receiver
}

output "this" {
  value = azurerm_monitor_action_group.this
}
```

[top](#index)