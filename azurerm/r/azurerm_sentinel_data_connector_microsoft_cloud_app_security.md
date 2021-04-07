# azurerm_sentinel_data_connector_microsoft_cloud_app_security

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
module "azurerm_sentinel_data_connector_microsoft_cloud_app_security" {
  source = "./modules/azurerm/r/azurerm_sentinel_data_connector_microsoft_cloud_app_security"

  # alerts_enabled - (optional) is a type of bool
  alerts_enabled = null
  # discovery_logs_enabled - (optional) is a type of bool
  discovery_logs_enabled = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # tenant_id - (optional) is a type of string
  tenant_id = null

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
variable "alerts_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "discovery_logs_enabled" {
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

variable "tenant_id" {
  description = "(optional)"
  type        = string
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
resource "azurerm_sentinel_data_connector_microsoft_cloud_app_security" "this" {
  # alerts_enabled - (optional) is a type of bool
  alerts_enabled = var.alerts_enabled
  # discovery_logs_enabled - (optional) is a type of bool
  discovery_logs_enabled = var.discovery_logs_enabled
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = var.log_analytics_workspace_id
  # name - (required) is a type of string
  name = var.name
  # tenant_id - (optional) is a type of string
  tenant_id = var.tenant_id

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
  value       = azurerm_sentinel_data_connector_microsoft_cloud_app_security.this.id
}

output "tenant_id" {
  description = "returns a string"
  value       = azurerm_sentinel_data_connector_microsoft_cloud_app_security.this.tenant_id
}

output "this" {
  value = azurerm_sentinel_data_connector_microsoft_cloud_app_security.this
}
```

[top](#index)