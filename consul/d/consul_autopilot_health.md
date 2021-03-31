# consul_autopilot_health

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
module "consul_autopilot_health" {
  source = "./modules/consul/d/consul_autopilot_health"

  # datacenter - (optional) is a type of string
  datacenter = null
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
```

[top](#index)

### Datasource

```terraform
data "consul_autopilot_health" "this" {
  datacenter = var.datacenter
}
```

[top](#index)

### Outputs

```terraform
output "failure_tolerance" {
  description = "returns a number"
  value       = data.consul_autopilot_health.this.failure_tolerance
}

output "healthy" {
  description = "returns a bool"
  value       = data.consul_autopilot_health.this.healthy
}

output "id" {
  description = "returns a string"
  value       = data.consul_autopilot_health.this.id
}

output "servers" {
  description = "returns a list of object"
  value       = data.consul_autopilot_health.this.servers
}

output "this" {
  value = consul_autopilot_health.this
}
```

[top](#index)