# azurerm_lb_probe

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
module "azurerm_lb_probe" {
  source = "./modules/azurerm/r/azurerm_lb_probe"

  # interval_in_seconds - (optional) is a type of number
  interval_in_seconds = null
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # number_of_probes - (optional) is a type of number
  number_of_probes = null
  # port - (required) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # request_path - (optional) is a type of string
  request_path = null
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
variable "interval_in_seconds" {
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

variable "number_of_probes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_path" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_lb_probe" "this" {
  interval_in_seconds = var.interval_in_seconds
  loadbalancer_id     = var.loadbalancer_id
  name                = var.name
  number_of_probes    = var.number_of_probes
  port                = var.port
  protocol            = var.protocol
  request_path        = var.request_path
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
output "id" {
  description = "returns a string"
  value       = azurerm_lb_probe.this.id
}

output "load_balancer_rules" {
  description = "returns a set of string"
  value       = azurerm_lb_probe.this.load_balancer_rules
}

output "protocol" {
  description = "returns a string"
  value       = azurerm_lb_probe.this.protocol
}

output "this" {
  value = azurerm_lb_probe.this
}
```

[top](#index)