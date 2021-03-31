# azurerm_lb_nat_pool

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
module "azurerm_lb_nat_pool" {
  source = "./modules/azurerm/r/azurerm_lb_nat_pool"

  # backend_port - (required) is a type of number
  backend_port = null
  # frontend_ip_configuration_name - (required) is a type of string
  frontend_ip_configuration_name = null
  # frontend_port_end - (required) is a type of number
  frontend_port_end = null
  # frontend_port_start - (required) is a type of number
  frontend_port_start = null
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
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
variable "backend_port" {
  description = "(required)"
  type        = number
}

variable "frontend_ip_configuration_name" {
  description = "(required)"
  type        = string
}

variable "frontend_port_end" {
  description = "(required)"
  type        = number
}

variable "frontend_port_start" {
  description = "(required)"
  type        = number
}

variable "loadbalancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol" {
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
resource "azurerm_lb_nat_pool" "this" {
  backend_port                   = var.backend_port
  frontend_ip_configuration_name = var.frontend_ip_configuration_name
  frontend_port_end              = var.frontend_port_end
  frontend_port_start            = var.frontend_port_start
  loadbalancer_id                = var.loadbalancer_id
  name                           = var.name
  protocol                       = var.protocol
  resource_group_name            = var.resource_group_name

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
output "frontend_ip_configuration_id" {
  description = "returns a string"
  value       = azurerm_lb_nat_pool.this.frontend_ip_configuration_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_lb_nat_pool.this.id
}

output "this" {
  value = azurerm_lb_nat_pool.this
}
```

[top](#index)