# azurerm_sentinel_data_connector_azure_active_directory

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
module "azurerm_sentinel_data_connector_azure_active_directory" {
  source = "./modules/azurerm/r/azurerm_sentinel_data_connector_azure_active_directory"

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
  }]
}
```

[top](#index)

### Variables

```terraform
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_sentinel_data_connector_azure_active_directory" "this" {
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name
  tenant_id                  = var.tenant_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_sentinel_data_connector_azure_active_directory.this.id
}

output "tenant_id" {
  description = "returns a string"
  value       = azurerm_sentinel_data_connector_azure_active_directory.this.tenant_id
}

output "this" {
  value = azurerm_sentinel_data_connector_azure_active_directory.this
}
```

[top](#index)