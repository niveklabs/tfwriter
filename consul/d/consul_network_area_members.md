# consul_network_area_members

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "consul_network_area_members" {
  source = "./modules/consul/d/consul_network_area_members"

  # datacenter - (optional) is a type of string
  datacenter = null
  # token - (optional) is a type of string
  token = null
  # uuid - (required) is a type of string
  uuid = null
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

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "consul_network_area_members" "this" {
  datacenter = var.datacenter
  token      = var.token
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = data.consul_network_area_members.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_network_area_members.this.id
}

output "members" {
  description = "returns a list of object"
  value       = data.consul_network_area_members.this.members
}

output "this" {
  value = consul_network_area_members.this
}
```

[top](#index)