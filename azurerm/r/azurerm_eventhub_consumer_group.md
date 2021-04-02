# azurerm_eventhub_consumer_group

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
module "azurerm_eventhub_consumer_group" {
  source = "./modules/azurerm/r/azurerm_eventhub_consumer_group"

  # eventhub_name - (required) is a type of string
  eventhub_name = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # user_metadata - (optional) is a type of string
  user_metadata = null

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

variable "user_metadata" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_eventhub_consumer_group" "this" {
  eventhub_name       = var.eventhub_name
  name                = var.name
  namespace_name      = var.namespace_name
  resource_group_name = var.resource_group_name
  user_metadata       = var.user_metadata

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
  value       = azurerm_eventhub_consumer_group.this.id
}

output "this" {
  value = azurerm_eventhub_consumer_group.this
}
```

[top](#index)