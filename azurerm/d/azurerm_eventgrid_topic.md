# azurerm_eventgrid_topic

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_eventgrid_topic" {
  source = "./modules/azurerm/d/azurerm_eventgrid_topic"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
data "azurerm_eventgrid_topic" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

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
output "endpoint" {
  description = "returns a string"
  value       = data.azurerm_eventgrid_topic.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_eventgrid_topic.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_eventgrid_topic.this.location
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurerm_eventgrid_topic.this.primary_access_key
  sensitive   = true
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurerm_eventgrid_topic.this.secondary_access_key
  sensitive   = true
}

output "this" {
  value = azurerm_eventgrid_topic.this
}
```

[top](#index)