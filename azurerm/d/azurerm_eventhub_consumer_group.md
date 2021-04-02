# azurerm_eventhub_consumer_group

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
module "azurerm_eventhub_consumer_group" {
  source = "./modules/azurerm/d/azurerm_eventhub_consumer_group"

  # eventhub_name - (required) is a type of string
  eventhub_name = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
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
variable "eventhub_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
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
data "azurerm_eventhub_consumer_group" "this" {
  eventhub_name       = var.eventhub_name
  name                = var.name
  namespace_name      = var.namespace_name
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_eventhub_consumer_group.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_eventhub_consumer_group.this.location
}

output "user_metadata" {
  description = "returns a string"
  value       = data.azurerm_eventhub_consumer_group.this.user_metadata
}

output "this" {
  value = azurerm_eventhub_consumer_group.this
}
```

[top](#index)