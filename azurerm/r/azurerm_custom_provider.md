# azurerm_custom_provider

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
module "azurerm_custom_provider" {
  source = "./modules/azurerm/r/azurerm_custom_provider"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  action = [{
    endpoint = null
    name     = null
  }]

  resource_type = [{
    endpoint     = null
    name         = null
    routing_type = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  validation = [{
    specification = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      endpoint = string
      name     = string
    }
  ))
  default = []
}

variable "resource_type" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      endpoint     = string
      name         = string
      routing_type = string
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

variable "validation" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      specification = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_custom_provider" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "action" {
    for_each = var.action
    content {
      # endpoint - (required) is a type of string
      endpoint = action.value["endpoint"]
      # name - (required) is a type of string
      name = action.value["name"]
    }
  }

  dynamic "resource_type" {
    for_each = var.resource_type
    content {
      # endpoint - (required) is a type of string
      endpoint = resource_type.value["endpoint"]
      # name - (required) is a type of string
      name = resource_type.value["name"]
      # routing_type - (optional) is a type of string
      routing_type = resource_type.value["routing_type"]
    }
  }

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

  dynamic "validation" {
    for_each = var.validation
    content {
      # specification - (required) is a type of string
      specification = validation.value["specification"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_custom_provider.this.id
}

output "this" {
  value = azurerm_custom_provider.this
}
```

[top](#index)