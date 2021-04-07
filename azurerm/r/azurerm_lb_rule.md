# azurerm_lb_rule

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
module "azurerm_lb_rule" {
  source = "./modules/azurerm/r/azurerm_lb_rule"

  # backend_address_pool_id - (optional) is a type of string
  backend_address_pool_id = null
  # backend_port - (required) is a type of number
  backend_port = null
  # disable_outbound_snat - (optional) is a type of bool
  disable_outbound_snat = null
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
  # load_distribution - (optional) is a type of string
  load_distribution = null
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # probe_id - (optional) is a type of string
  probe_id = null
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
variable "backend_address_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backend_port" {
  description = "(required)"
  type        = number
}

variable "disable_outbound_snat" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "load_distribution" {
  description = "(optional)"
  type        = string
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

variable "probe_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_lb_rule" "this" {
  # backend_address_pool_id - (optional) is a type of string
  backend_address_pool_id = var.backend_address_pool_id
  # backend_port - (required) is a type of number
  backend_port = var.backend_port
  # disable_outbound_snat - (optional) is a type of bool
  disable_outbound_snat = var.disable_outbound_snat
  # enable_floating_ip - (optional) is a type of bool
  enable_floating_ip = var.enable_floating_ip
  # enable_tcp_reset - (optional) is a type of bool
  enable_tcp_reset = var.enable_tcp_reset
  # frontend_ip_configuration_name - (required) is a type of string
  frontend_ip_configuration_name = var.frontend_ip_configuration_name
  # frontend_port - (required) is a type of number
  frontend_port = var.frontend_port
  # idle_timeout_in_minutes - (optional) is a type of number
  idle_timeout_in_minutes = var.idle_timeout_in_minutes
  # load_distribution - (optional) is a type of string
  load_distribution = var.load_distribution
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = var.loadbalancer_id
  # name - (required) is a type of string
  name = var.name
  # probe_id - (optional) is a type of string
  probe_id = var.probe_id
  # protocol - (required) is a type of string
  protocol = var.protocol
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
output "backend_address_pool_id" {
  description = "returns a string"
  value       = azurerm_lb_rule.this.backend_address_pool_id
}

output "frontend_ip_configuration_id" {
  description = "returns a string"
  value       = azurerm_lb_rule.this.frontend_ip_configuration_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_lb_rule.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = azurerm_lb_rule.this.idle_timeout_in_minutes
}

output "load_distribution" {
  description = "returns a string"
  value       = azurerm_lb_rule.this.load_distribution
}

output "probe_id" {
  description = "returns a string"
  value       = azurerm_lb_rule.this.probe_id
}

output "this" {
  value = azurerm_lb_rule.this
}
```

[top](#index)