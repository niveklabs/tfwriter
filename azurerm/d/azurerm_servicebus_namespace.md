# azurerm_servicebus_namespace

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
module "azurerm_servicebus_namespace" {
  source = "./modules/azurerm/d/azurerm_servicebus_namespace"

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
data "azurerm_servicebus_namespace" "this" {
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
output "capacity" {
  description = "returns a number"
  value       = data.azurerm_servicebus_namespace.this.capacity
}

output "default_primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.default_primary_connection_string
  sensitive   = true
}

output "default_primary_key" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.default_primary_key
  sensitive   = true
}

output "default_secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.default_secondary_connection_string
  sensitive   = true
}

output "default_secondary_key" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.default_secondary_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.location
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_servicebus_namespace.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_servicebus_namespace.this.tags
}

output "zone_redundant" {
  description = "returns a bool"
  value       = data.azurerm_servicebus_namespace.this.zone_redundant
}

output "this" {
  value = azurerm_servicebus_namespace.this
}
```

[top](#index)