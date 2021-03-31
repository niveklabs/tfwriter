# azurerm_lb_rule

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
module "azurerm_lb_rule" {
  source = "./modules/azurerm/d/azurerm_lb_rule"

  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_lb_rule" "this" {
  loadbalancer_id     = var.loadbalancer_id
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "backend_address_pool_id" {
  description = "returns a string"
  value       = data.azurerm_lb_rule.this.backend_address_pool_id
}

output "backend_port" {
  description = "returns a number"
  value       = data.azurerm_lb_rule.this.backend_port
}

output "disable_outbound_snat" {
  description = "returns a bool"
  value       = data.azurerm_lb_rule.this.disable_outbound_snat
}

output "enable_floating_ip" {
  description = "returns a bool"
  value       = data.azurerm_lb_rule.this.enable_floating_ip
}

output "enable_tcp_reset" {
  description = "returns a bool"
  value       = data.azurerm_lb_rule.this.enable_tcp_reset
}

output "frontend_ip_configuration_name" {
  description = "returns a string"
  value       = data.azurerm_lb_rule.this.frontend_ip_configuration_name
}

output "frontend_port" {
  description = "returns a number"
  value       = data.azurerm_lb_rule.this.frontend_port
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_lb_rule.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = data.azurerm_lb_rule.this.idle_timeout_in_minutes
}

output "load_distribution" {
  description = "returns a string"
  value       = data.azurerm_lb_rule.this.load_distribution
}

output "probe_id" {
  description = "returns a string"
  value       = data.azurerm_lb_rule.this.probe_id
}

output "protocol" {
  description = "returns a string"
  value       = data.azurerm_lb_rule.this.protocol
}

output "this" {
  value = azurerm_lb_rule.this
}
```

[top](#index)