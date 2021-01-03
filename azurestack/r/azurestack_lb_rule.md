# azurestack_lb_rule

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
module "azurestack_lb_rule" {
  source = "./modules/azurestack/r/azurestack_lb_rule"

  # backend_address_pool_id - (optional) is a type of string
  backend_address_pool_id = null
  # backend_port - (required) is a type of number
  backend_port = null
  # enable_floating_ip - (optional) is a type of bool
  enable_floating_ip = null
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
```

[top](#index)

### Resource

```terraform
resource "azurestack_lb_rule" "this" {
  backend_address_pool_id        = var.backend_address_pool_id
  backend_port                   = var.backend_port
  enable_floating_ip             = var.enable_floating_ip
  frontend_ip_configuration_name = var.frontend_ip_configuration_name
  frontend_port                  = var.frontend_port
  idle_timeout_in_minutes        = var.idle_timeout_in_minutes
  load_distribution              = var.load_distribution
  loadbalancer_id                = var.loadbalancer_id
  name                           = var.name
  probe_id                       = var.probe_id
  protocol                       = var.protocol
  resource_group_name            = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "backend_address_pool_id" {
  description = "returns a string"
  value       = azurestack_lb_rule.this.backend_address_pool_id
}

output "frontend_ip_configuration_id" {
  description = "returns a string"
  value       = azurestack_lb_rule.this.frontend_ip_configuration_id
}

output "id" {
  description = "returns a string"
  value       = azurestack_lb_rule.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = azurestack_lb_rule.this.idle_timeout_in_minutes
}

output "load_distribution" {
  description = "returns a string"
  value       = azurestack_lb_rule.this.load_distribution
}

output "probe_id" {
  description = "returns a string"
  value       = azurestack_lb_rule.this.probe_id
}

output "this" {
  value = azurestack_lb_rule.this
}
```

[top](#index)