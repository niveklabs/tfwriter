# azurerm_api_management_logger

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_api_management_logger" {
  source = "./modules/azurerm/r/azurerm_api_management_logger"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # buffered - (optional) is a type of bool
  buffered = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  application_insights = [{
    instrumentation_key = null
  }]

  eventhub = [{
    connection_string = null
    name              = null
  }]

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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "buffered" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "application_insights" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instrumentation_key = string
    }
  ))
  default = []
}

variable "eventhub" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_string = string
      name              = string
    }
  ))
  default = []
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
resource "azurerm_api_management_logger" "this" {
  api_management_name = var.api_management_name
  buffered            = var.buffered
  description         = var.description
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "application_insights" {
    for_each = var.application_insights
    content {
      instrumentation_key = application_insights.value["instrumentation_key"]
    }
  }

  dynamic "eventhub" {
    for_each = var.eventhub
    content {
      connection_string = eventhub.value["connection_string"]
      name              = eventhub.value["name"]
    }
  }

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
  value       = azurerm_api_management_logger.this.id
}

output "this" {
  value = azurerm_api_management_logger.this
}
```

[top](#index)