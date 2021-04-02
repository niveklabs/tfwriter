# azurerm_application_insights

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
module "azurerm_application_insights" {
  source = "./modules/azurerm/r/azurerm_application_insights"

  # application_type - (required) is a type of string
  application_type = null
  # daily_data_cap_in_gb - (optional) is a type of number
  daily_data_cap_in_gb = null
  # daily_data_cap_notifications_disabled - (optional) is a type of bool
  daily_data_cap_notifications_disabled = null
  # disable_ip_masking - (optional) is a type of bool
  disable_ip_masking = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # retention_in_days - (optional) is a type of number
  retention_in_days = null
  # sampling_percentage - (optional) is a type of number
  sampling_percentage = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "application_type" {
  description = "(required)"
  type        = string
}

variable "daily_data_cap_in_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "daily_data_cap_notifications_disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_ip_masking" {
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

variable "retention_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sampling_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "azurerm_application_insights" "this" {
  application_type                      = var.application_type
  daily_data_cap_in_gb                  = var.daily_data_cap_in_gb
  daily_data_cap_notifications_disabled = var.daily_data_cap_notifications_disabled
  disable_ip_masking                    = var.disable_ip_masking
  location                              = var.location
  name                                  = var.name
  resource_group_name                   = var.resource_group_name
  retention_in_days                     = var.retention_in_days
  sampling_percentage                   = var.sampling_percentage
  tags                                  = var.tags

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
output "app_id" {
  description = "returns a string"
  value       = azurerm_application_insights.this.app_id
}

output "connection_string" {
  description = "returns a string"
  value       = azurerm_application_insights.this.connection_string
  sensitive   = true
}

output "daily_data_cap_in_gb" {
  description = "returns a number"
  value       = azurerm_application_insights.this.daily_data_cap_in_gb
}

output "daily_data_cap_notifications_disabled" {
  description = "returns a bool"
  value       = azurerm_application_insights.this.daily_data_cap_notifications_disabled
}

output "id" {
  description = "returns a string"
  value       = azurerm_application_insights.this.id
}

output "instrumentation_key" {
  description = "returns a string"
  value       = azurerm_application_insights.this.instrumentation_key
  sensitive   = true
}

output "this" {
  value = azurerm_application_insights.this
}
```

[top](#index)