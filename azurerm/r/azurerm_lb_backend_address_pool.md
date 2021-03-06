# azurerm_lb_backend_address_pool

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
module "azurerm_lb_backend_address_pool" {
  source = "./modules/azurerm/r/azurerm_lb_backend_address_pool"

  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (optional) is a type of string
  resource_group_name = null

  backend_address = [{
    ip_address         = null
    name               = null
    virtual_network_id = null
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
variable "loadbalancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backend_address" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address         = string
      name               = string
      virtual_network_id = string
    }
  ))
  default = []
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
resource "azurerm_lb_backend_address_pool" "this" {
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = var.loadbalancer_id
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (optional) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "backend_address" {
    for_each = var.backend_address
    content {
      # ip_address - (required) is a type of string
      ip_address = backend_address.value["ip_address"]
      # name - (required) is a type of string
      name = backend_address.value["name"]
      # virtual_network_id - (required) is a type of string
      virtual_network_id = backend_address.value["virtual_network_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "backend_ip_configurations" {
  description = "returns a list of string"
  value       = azurerm_lb_backend_address_pool.this.backend_ip_configurations
}

output "id" {
  description = "returns a string"
  value       = azurerm_lb_backend_address_pool.this.id
}

output "load_balancing_rules" {
  description = "returns a list of string"
  value       = azurerm_lb_backend_address_pool.this.load_balancing_rules
}

output "outbound_rules" {
  description = "returns a list of string"
  value       = azurerm_lb_backend_address_pool.this.outbound_rules
}

output "resource_group_name" {
  description = "returns a string"
  value       = azurerm_lb_backend_address_pool.this.resource_group_name
}

output "this" {
  value = azurerm_lb_backend_address_pool.this
}
```

[top](#index)