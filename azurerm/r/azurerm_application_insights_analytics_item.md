# azurerm_application_insights_analytics_item

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
module "azurerm_application_insights_analytics_item" {
  source = "./modules/azurerm/r/azurerm_application_insights_analytics_item"

  # application_insights_id - (required) is a type of string
  application_insights_id = null
  # content - (required) is a type of string
  content = null
  # function_alias - (optional) is a type of string
  function_alias = null
  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
  # type - (required) is a type of string
  type = null

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
variable "application_insights_id" {
  description = "(required)"
  type        = string
}

variable "content" {
  description = "(required)"
  type        = string
}

variable "function_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
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
resource "azurerm_application_insights_analytics_item" "this" {
  application_insights_id = var.application_insights_id
  content                 = var.content
  function_alias          = var.function_alias
  name                    = var.name
  scope                   = var.scope
  type                    = var.type

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
  value       = azurerm_application_insights_analytics_item.this.id
}

output "time_created" {
  description = "returns a string"
  value       = azurerm_application_insights_analytics_item.this.time_created
}

output "time_modified" {
  description = "returns a string"
  value       = azurerm_application_insights_analytics_item.this.time_modified
}

output "version" {
  description = "returns a string"
  value       = azurerm_application_insights_analytics_item.this.version
}

output "this" {
  value = azurerm_application_insights_analytics_item.this
}
```

[top](#index)