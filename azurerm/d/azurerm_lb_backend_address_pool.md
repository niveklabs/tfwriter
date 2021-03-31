# azurerm_lb_backend_address_pool

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
module "azurerm_lb_backend_address_pool" {
  source = "./modules/azurerm/d/azurerm_lb_backend_address_pool"

  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    read = null
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
data "azurerm_lb_backend_address_pool" "this" {
  loadbalancer_id = var.loadbalancer_id
  name            = var.name

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
output "backend_address" {
  description = "returns a list of object"
  value       = data.azurerm_lb_backend_address_pool.this.backend_address
}

output "backend_ip_configurations" {
  description = "returns a list of object"
  value       = data.azurerm_lb_backend_address_pool.this.backend_ip_configurations
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_lb_backend_address_pool.this.id
}

output "load_balancing_rules" {
  description = "returns a list of string"
  value       = data.azurerm_lb_backend_address_pool.this.load_balancing_rules
}

output "outbound_rules" {
  description = "returns a list of string"
  value       = data.azurerm_lb_backend_address_pool.this.outbound_rules
}

output "this" {
  value = azurerm_lb_backend_address_pool.this
}
```

[top](#index)