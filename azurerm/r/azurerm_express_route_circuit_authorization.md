# azurerm_express_route_circuit_authorization

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
module "azurerm_express_route_circuit_authorization" {
  source = "./modules/azurerm/r/azurerm_express_route_circuit_authorization"

  # express_route_circuit_name - (required) is a type of string
  express_route_circuit_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "express_route_circuit_name" {
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
resource "azurerm_express_route_circuit_authorization" "this" {
  express_route_circuit_name = var.express_route_circuit_name
  name                       = var.name
  resource_group_name        = var.resource_group_name

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
output "authorization_key" {
  description = "returns a string"
  value       = azurerm_express_route_circuit_authorization.this.authorization_key
  sensitive   = true
}

output "authorization_use_status" {
  description = "returns a string"
  value       = azurerm_express_route_circuit_authorization.this.authorization_use_status
}

output "id" {
  description = "returns a string"
  value       = azurerm_express_route_circuit_authorization.this.id
}

output "this" {
  value = azurerm_express_route_circuit_authorization.this
}
```

[top](#index)