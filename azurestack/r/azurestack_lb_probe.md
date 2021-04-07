# azurestack_lb_probe

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
module "azurestack_lb_probe" {
  source = "./modules/azurestack/r/azurestack_lb_probe"

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
```

[top](#index)

### Resource

```terraform
resource "azurestack_lb_probe" "this" {
  # interval_in_seconds - (optional) is a type of number
  interval_in_seconds = var.interval_in_seconds
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = var.loadbalancer_id
  # name - (required) is a type of string
  name = var.name
  # number_of_probes - (optional) is a type of number
  number_of_probes = var.number_of_probes
  # port - (required) is a type of number
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # request_path - (optional) is a type of string
  request_path = var.request_path
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_lb_probe.this.id
}

output "load_balancer_rules" {
  description = "returns a set of string"
  value       = azurestack_lb_probe.this.load_balancer_rules
}

output "protocol" {
  description = "returns a string"
  value       = azurestack_lb_probe.this.protocol
}

output "this" {
  value = azurestack_lb_probe.this
}
```

[top](#index)