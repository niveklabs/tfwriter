# azurerm_express_route_circuit

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
module "azurerm_express_route_circuit" {
  source = "./modules/azurerm/d/azurerm_express_route_circuit"

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
data "azurerm_express_route_circuit" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_express_route_circuit.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_express_route_circuit.this.location
}

output "peerings" {
  description = "returns a list of object"
  value       = data.azurerm_express_route_circuit.this.peerings
}

output "service_key" {
  description = "returns a string"
  value       = data.azurerm_express_route_circuit.this.service_key
}

output "service_provider_properties" {
  description = "returns a list of object"
  value       = data.azurerm_express_route_circuit.this.service_provider_properties
}

output "service_provider_provisioning_state" {
  description = "returns a string"
  value       = data.azurerm_express_route_circuit.this.service_provider_provisioning_state
}

output "sku" {
  description = "returns a list of object"
  value       = data.azurerm_express_route_circuit.this.sku
}

output "this" {
  value = azurerm_express_route_circuit.this
}
```

[top](#index)