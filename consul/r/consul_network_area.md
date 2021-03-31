# consul_network_area

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
module "consul_network_area" {
  source = "./modules/consul/r/consul_network_area"

  # datacenter - (optional) is a type of string
  datacenter = null
  # peer_datacenter - (required) is a type of string
  peer_datacenter = null
  # retry_join - (optional) is a type of list of string
  retry_join = []
  # token - (optional) is a type of string
  token = null
  # use_tls - (optional) is a type of bool
  use_tls = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_datacenter" {
  description = "(required)"
  type        = string
}

variable "retry_join" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_tls" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_network_area" "this" {
  datacenter      = var.datacenter
  peer_datacenter = var.peer_datacenter
  retry_join      = var.retry_join
  token           = var.token
  use_tls         = var.use_tls
}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = consul_network_area.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_network_area.this.id
}

output "this" {
  value = consul_network_area.this
}
```

[top](#index)