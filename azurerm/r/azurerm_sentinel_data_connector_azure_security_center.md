# azurerm_sentinel_data_connector_azure_security_center

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
module "azurerm_sentinel_data_connector_azure_security_center" {
  source = "./modules/azurerm/r/azurerm_sentinel_data_connector_azure_security_center"

  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # subscription_id - (optional) is a type of string
  subscription_id = null

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

variable "subscription_id" {
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
resource "azurerm_sentinel_data_connector_azure_security_center" "this" {
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name
  subscription_id            = var.subscription_id

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
  value       = azurerm_sentinel_data_connector_azure_security_center.this.id
}

output "subscription_id" {
  description = "returns a string"
  value       = azurerm_sentinel_data_connector_azure_security_center.this.subscription_id
}

output "this" {
  value = azurerm_sentinel_data_connector_azure_security_center.this
}
```

[top](#index)