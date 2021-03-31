# azurerm_lb_outbound_rule

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
module "azurerm_lb_outbound_rule" {
  source = "./modules/azurerm/r/azurerm_lb_outbound_rule"

  # allocated_outbound_ports - (optional) is a type of number
  allocated_outbound_ports = null
  # backend_address_pool_id - (required) is a type of string
  backend_address_pool_id = null
  # enable_tcp_reset - (optional) is a type of bool
  enable_tcp_reset = null
  # idle_timeout_in_minutes - (optional) is a type of number
  idle_timeout_in_minutes = null
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  frontend_ip_configuration = [{
    id   = null
    name = null
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
variable "allocated_outbound_ports" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backend_address_pool_id" {
  description = "(required)"
  type        = string
}

variable "enable_tcp_reset" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "idle_timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
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

variable "frontend_ip_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
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
resource "azurerm_lb_outbound_rule" "this" {
  allocated_outbound_ports = var.allocated_outbound_ports
  backend_address_pool_id  = var.backend_address_pool_id
  enable_tcp_reset         = var.enable_tcp_reset
  idle_timeout_in_minutes  = var.idle_timeout_in_minutes
  loadbalancer_id          = var.loadbalancer_id
  name                     = var.name
  protocol                 = var.protocol
  resource_group_name      = var.resource_group_name

  dynamic "frontend_ip_configuration" {
    for_each = var.frontend_ip_configuration
    content {
      name = frontend_ip_configuration.value["name"]
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
  value       = azurerm_lb_outbound_rule.this.id
}

output "this" {
  value = azurerm_lb_outbound_rule.this
}
```

[top](#index)