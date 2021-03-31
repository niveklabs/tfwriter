# azurerm_application_insights

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
module "azurerm_application_insights" {
  source = "./modules/azurerm/d/azurerm_application_insights"

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
data "azurerm_application_insights" "this" {
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
output "app_id" {
  description = "returns a string"
  value       = data.azurerm_application_insights.this.app_id
}

output "application_type" {
  description = "returns a string"
  value       = data.azurerm_application_insights.this.application_type
}

output "connection_string" {
  description = "returns a string"
  value       = data.azurerm_application_insights.this.connection_string
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_application_insights.this.id
}

output "instrumentation_key" {
  description = "returns a string"
  value       = data.azurerm_application_insights.this.instrumentation_key
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_application_insights.this.location
}

output "retention_in_days" {
  description = "returns a number"
  value       = data.azurerm_application_insights.this.retention_in_days
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_application_insights.this.tags
}

output "this" {
  value = azurerm_application_insights.this
}
```

[top](#index)