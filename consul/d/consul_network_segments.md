# consul_network_segments

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
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_network_segments" {
  source = "./modules/consul/d/consul_network_segments"

  # datacenter - (optional) is a type of string
  datacenter = null
  # token - (optional) is a type of string
  token = null
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
```

[top](#index)

### Datasource

```terraform
data "consul_network_segments" "this" {
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # token - (optional) is a type of string
  token = var.token
}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = data.consul_network_segments.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = data.consul_network_segments.this.id
}

output "segments" {
  description = "returns a list of string"
  value       = data.consul_network_segments.this.segments
}

output "this" {
  value = consul_network_segments.this
}
```

[top](#index)