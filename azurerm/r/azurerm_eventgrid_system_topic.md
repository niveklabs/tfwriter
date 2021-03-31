# azurerm_eventgrid_system_topic

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
module "azurerm_eventgrid_system_topic" {
  source = "./modules/azurerm/r/azurerm_eventgrid_system_topic"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_arm_resource_id - (required) is a type of string
  source_arm_resource_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # topic_type - (required) is a type of string
  topic_type = null

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

variable "source_arm_resource_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "topic_type" {
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
resource "azurerm_eventgrid_system_topic" "this" {
  location               = var.location
  name                   = var.name
  resource_group_name    = var.resource_group_name
  source_arm_resource_id = var.source_arm_resource_id
  tags                   = var.tags
  topic_type             = var.topic_type

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
  value       = azurerm_eventgrid_system_topic.this.id
}

output "metric_arm_resource_id" {
  description = "returns a string"
  value       = azurerm_eventgrid_system_topic.this.metric_arm_resource_id
}

output "this" {
  value = azurerm_eventgrid_system_topic.this
}
```

[top](#index)