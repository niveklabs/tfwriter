# consul_node

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.10.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_node" {
  source = "./modules/consul/r/consul_node"

  # address - (required) is a type of string
  address = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # meta - (optional) is a type of map of string
  meta = {}
  # name - (required) is a type of string
  name = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_node" "this" {
  address    = var.address
  datacenter = var.datacenter
  meta       = var.meta
  name       = var.name
  token      = var.token
}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = consul_node.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_node.this.id
}

output "this" {
  value = consul_node.this
}
```

[top](#index)