# azurerm_lb_nat_rule

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
module "azurerm_lb_nat_rule" {
  source = "./modules/azurerm/r/azurerm_lb_nat_rule"

  # backend_port - (required) is a type of number
  backend_port = null
  # enable_floating_ip - (optional) is a type of bool
  enable_floating_ip = null
  # enable_tcp_reset - (optional) is a type of bool
  enable_tcp_reset = null
  # frontend_ip_configuration_name - (required) is a type of string
  frontend_ip_configuration_name = null
  # frontend_port - (required) is a type of number
  frontend_port = null
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

variable "enable_floating_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_tcp_reset" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "frontend_ip_configuration_name" {
  description = "(required)"
  type        = string
}

variable "frontend_port" {
  description = "(required)"
  type        = number
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
resource "azurerm_lb_nat_rule" "this" {
  backend_port                   = var.backend_port
  enable_floating_ip             = var.enable_floating_ip
  enable_tcp_reset               = var.enable_tcp_reset
  frontend_ip_configuration_name = var.frontend_ip_configuration_name
  frontend_port                  = var.frontend_port
  idle_timeout_in_minutes        = var.idle_timeout_in_minutes
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
output "backend_ip_configuration_id" {
  description = "returns a string"
  value       = azurerm_lb_nat_rule.this.backend_ip_configuration_id
}

output "enable_floating_ip" {
  description = "returns a bool"
  value       = azurerm_lb_nat_rule.this.enable_floating_ip
}

output "frontend_ip_configuration_id" {
  description = "returns a string"
  value       = azurerm_lb_nat_rule.this.frontend_ip_configuration_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_lb_nat_rule.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = azurerm_lb_nat_rule.this.idle_timeout_in_minutes
}

output "this" {
  value = azurerm_lb_nat_rule.this
}
```

[top](#index)