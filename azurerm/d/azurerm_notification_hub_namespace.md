# azurerm_notification_hub_namespace

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
module "azurerm_notification_hub_namespace" {
  source = "./modules/azurerm/d/azurerm_notification_hub_namespace"

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
data "azurerm_notification_hub_namespace" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "enabled" {
  description = "returns a bool"
  value       = data.azurerm_notification_hub_namespace.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_notification_hub_namespace.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_notification_hub_namespace.this.location
}

output "namespace_type" {
  description = "returns a string"
  value       = data.azurerm_notification_hub_namespace.this.namespace_type
}

output "servicebus_endpoint" {
  description = "returns a string"
  value       = data.azurerm_notification_hub_namespace.this.servicebus_endpoint
}

output "sku" {
  description = "returns a list of object"
  value       = data.azurerm_notification_hub_namespace.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_notification_hub_namespace.this.tags
}

output "this" {
  value = azurerm_notification_hub_namespace.this
}
```

[top](#index)