# azurerm_app_service_hybrid_connection

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
module "azurerm_app_service_hybrid_connection" {
  source = "./modules/azurerm/r/azurerm_app_service_hybrid_connection"

  # app_service_name - (required) is a type of string
  app_service_name = null
  # hostname - (required) is a type of string
  hostname = null
  # port - (required) is a type of number
  port = null
  # relay_id - (required) is a type of string
  relay_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # send_key_name - (optional) is a type of string
  send_key_name = null

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
variable "app_service_name" {
  description = "(required)"
  type        = string
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "relay_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "send_key_name" {
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
resource "azurerm_app_service_hybrid_connection" "this" {
  app_service_name    = var.app_service_name
  hostname            = var.hostname
  port                = var.port
  relay_id            = var.relay_id
  resource_group_name = var.resource_group_name
  send_key_name       = var.send_key_name

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
  value       = azurerm_app_service_hybrid_connection.this.id
}

output "namespace_name" {
  description = "returns a string"
  value       = azurerm_app_service_hybrid_connection.this.namespace_name
}

output "relay_name" {
  description = "returns a string"
  value       = azurerm_app_service_hybrid_connection.this.relay_name
}

output "send_key_value" {
  description = "returns a string"
  value       = azurerm_app_service_hybrid_connection.this.send_key_value
  sensitive   = true
}

output "service_bus_namespace" {
  description = "returns a string"
  value       = azurerm_app_service_hybrid_connection.this.service_bus_namespace
}

output "service_bus_suffix" {
  description = "returns a string"
  value       = azurerm_app_service_hybrid_connection.this.service_bus_suffix
}

output "this" {
  value = azurerm_app_service_hybrid_connection.this
}
```

[top](#index)