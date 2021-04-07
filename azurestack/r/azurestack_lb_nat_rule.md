# azurestack_lb_nat_rule

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_lb_nat_rule" {
  source = "./modules/azurestack/r/azurestack_lb_nat_rule"

  # backend_port - (required) is a type of number
  backend_port = null
  # enable_floating_ip - (optional) is a type of bool
  enable_floating_ip = null
  # frontend_ip_configuration_name - (required) is a type of string
  frontend_ip_configuration_name = null
  # frontend_port - (required) is a type of number
  frontend_port = null
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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

variable "frontend_ip_configuration_name" {
  description = "(required)"
  type        = string
}

variable "frontend_port" {
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
```

[top](#index)

### Resource

```terraform
resource "azurestack_lb_nat_rule" "this" {
  # backend_port - (required) is a type of number
  backend_port = var.backend_port
  # enable_floating_ip - (optional) is a type of bool
  enable_floating_ip = var.enable_floating_ip
  # frontend_ip_configuration_name - (required) is a type of string
  frontend_ip_configuration_name = var.frontend_ip_configuration_name
  # frontend_port - (required) is a type of number
  frontend_port = var.frontend_port
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = var.loadbalancer_id
  # name - (required) is a type of string
  name = var.name
  # protocol - (required) is a type of string
  protocol = var.protocol
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "backend_ip_configuration_id" {
  description = "returns a string"
  value       = azurestack_lb_nat_rule.this.backend_ip_configuration_id
}

output "enable_floating_ip" {
  description = "returns a bool"
  value       = azurestack_lb_nat_rule.this.enable_floating_ip
}

output "frontend_ip_configuration_id" {
  description = "returns a string"
  value       = azurestack_lb_nat_rule.this.frontend_ip_configuration_id
}

output "id" {
  description = "returns a string"
  value       = azurestack_lb_nat_rule.this.id
}

output "this" {
  value = azurestack_lb_nat_rule.this
}
```

[top](#index)