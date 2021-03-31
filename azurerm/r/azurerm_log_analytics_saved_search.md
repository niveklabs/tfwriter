# azurerm_log_analytics_saved_search

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
module "azurerm_log_analytics_saved_search" {
  source = "./modules/azurerm/r/azurerm_log_analytics_saved_search"

  # category - (required) is a type of string
  category = null
  # display_name - (required) is a type of string
  display_name = null
  # function_alias - (optional) is a type of string
  function_alias = null
  # function_parameters - (optional) is a type of set of string
  function_parameters = []
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
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
variable "category" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "function_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "function_parameters" {
  description = "(optional)"
  type        = set(string)
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

variable "query" {
  description = "(required)"
  type        = string
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
resource "azurerm_log_analytics_saved_search" "this" {
  category                   = var.category
  display_name               = var.display_name
  function_alias             = var.function_alias
  function_parameters        = var.function_parameters
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name
  query                      = var.query
  tags                       = var.tags

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
  value       = azurerm_log_analytics_saved_search.this.id
}

output "this" {
  value = azurerm_log_analytics_saved_search.this
}
```

[top](#index)