# consul_agent_service

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
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_agent_service" {
  source = "./modules/consul/r/consul_agent_service"

  # address - (optional) is a type of string
  address = null
  # name - (required) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_agent_service" "this" {
  address = var.address
  name    = var.name
  port    = var.port
  tags    = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = consul_agent_service.this.address
}

output "id" {
  description = "returns a string"
  value       = consul_agent_service.this.id
}

output "this" {
  value = consul_agent_service.this
}
```

[top](#index)