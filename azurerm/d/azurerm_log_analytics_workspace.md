# azurerm_log_analytics_workspace

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_log_analytics_workspace" {
  source = "./modules/azurerm/d/azurerm_log_analytics_workspace"

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
data "azurerm_log_analytics_workspace" "this" {
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
output "daily_quota_gb" {
  description = "returns a number"
  value       = data.azurerm_log_analytics_workspace.this.daily_quota_gb
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.location
}

output "portal_url" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.portal_url
}

output "primary_shared_key" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.primary_shared_key
  sensitive   = true
}

output "retention_in_days" {
  description = "returns a number"
  value       = data.azurerm_log_analytics_workspace.this.retention_in_days
}

output "secondary_shared_key" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.secondary_shared_key
  sensitive   = true
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_log_analytics_workspace.this.tags
}

output "workspace_id" {
  description = "returns a string"
  value       = data.azurerm_log_analytics_workspace.this.workspace_id
}

output "this" {
  value = azurerm_log_analytics_workspace.this
}
```

[top](#index)