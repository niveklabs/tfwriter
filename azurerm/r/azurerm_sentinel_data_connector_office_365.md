# azurerm_sentinel_data_connector_office_365

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
module "azurerm_sentinel_data_connector_office_365" {
  source = "./modules/azurerm/r/azurerm_sentinel_data_connector_office_365"

  # exchange_enabled - (optional) is a type of bool
  exchange_enabled = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # sharepoint_enabled - (optional) is a type of bool
  sharepoint_enabled = null
  # teams_enabled - (optional) is a type of bool
  teams_enabled = null
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
variable "exchange_enabled" {
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

variable "sharepoint_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "teams_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
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
resource "azurerm_sentinel_data_connector_office_365" "this" {
  exchange_enabled           = var.exchange_enabled
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name
  sharepoint_enabled         = var.sharepoint_enabled
  teams_enabled              = var.teams_enabled
  tenant_id                  = var.tenant_id

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
  value       = azurerm_sentinel_data_connector_office_365.this.id
}

output "tenant_id" {
  description = "returns a string"
  value       = azurerm_sentinel_data_connector_office_365.this.tenant_id
}

output "this" {
  value = azurerm_sentinel_data_connector_office_365.this
}
```

[top](#index)