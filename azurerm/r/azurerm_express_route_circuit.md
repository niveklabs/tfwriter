# azurerm_express_route_circuit

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
module "azurerm_express_route_circuit" {
  source = "./modules/azurerm/r/azurerm_express_route_circuit"

  # allow_classic_operations - (optional) is a type of bool
  allow_classic_operations = null
  # bandwidth_in_mbps - (required) is a type of number
  bandwidth_in_mbps = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # peering_location - (required) is a type of string
  peering_location = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_provider_name - (required) is a type of string
  service_provider_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  sku = [{
    family = null
    tier   = null
  }]

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
variable "allow_classic_operations" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bandwidth_in_mbps" {
  description = "(required)"
  type        = number
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "peering_location" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_provider_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      family = string
      tier   = string
    }
  ))
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
resource "azurerm_express_route_circuit" "this" {
  allow_classic_operations = var.allow_classic_operations
  bandwidth_in_mbps        = var.bandwidth_in_mbps
  location                 = var.location
  name                     = var.name
  peering_location         = var.peering_location
  resource_group_name      = var.resource_group_name
  service_provider_name    = var.service_provider_name
  tags                     = var.tags

  dynamic "sku" {
    for_each = var.sku
    content {
      family = sku.value["family"]
      tier   = sku.value["tier"]
    }
  }

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
  value       = azurerm_express_route_circuit.this.id
}

output "service_key" {
  description = "returns a string"
  value       = azurerm_express_route_circuit.this.service_key
  sensitive   = true
}

output "service_provider_provisioning_state" {
  description = "returns a string"
  value       = azurerm_express_route_circuit.this.service_provider_provisioning_state
}

output "this" {
  value = azurerm_express_route_circuit.this
}
```

[top](#index)