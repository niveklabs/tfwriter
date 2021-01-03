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
    azurerm = ">= 2.41.0"
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
variable "loadbalancer_id" {
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
resource "azurerm_lb_backend_address_pool" "this" {
  loadbalancer_id     = var.loadbalancer_id
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "backend_ip_configurations" {
  description = "returns a set of string"
  value       = azurerm_lb_backend_address_pool.this.backend_ip_configurations
}

output "id" {
  description = "returns a string"
  value       = azurerm_lb_backend_address_pool.this.id
}

output "load_balancing_rules" {
  description = "returns a set of string"
  value       = azurerm_lb_backend_address_pool.this.load_balancing_rules
}

output "this" {
  value = azurerm_lb_backend_address_pool.this
}
```

[top](#index)