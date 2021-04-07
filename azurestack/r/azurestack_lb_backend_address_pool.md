# azurestack_lb_backend_address_pool

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
module "azurestack_lb_backend_address_pool" {
  source = "./modules/azurestack/r/azurestack_lb_backend_address_pool"

  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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
```

[top](#index)

### Resource

```terraform
resource "azurestack_lb_backend_address_pool" "this" {
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = var.loadbalancer_id
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "backend_ip_configurations" {
  description = "returns a set of string"
  value       = azurestack_lb_backend_address_pool.this.backend_ip_configurations
}

output "id" {
  description = "returns a string"
  value       = azurestack_lb_backend_address_pool.this.id
}

output "load_balancing_rules" {
  description = "returns a set of string"
  value       = azurestack_lb_backend_address_pool.this.load_balancing_rules
}

output "this" {
  value = azurestack_lb_backend_address_pool.this
}
```

[top](#index)