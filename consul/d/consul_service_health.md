# consul_service_health

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
module "consul_service_health" {
  source = "./modules/consul/d/consul_service_health"

  # datacenter - (optional) is a type of string
  datacenter = null
  # filter - (optional) is a type of string
  filter = null
  # name - (required) is a type of string
  name = null
  # near - (optional) is a type of string
  near = null
  # node_meta - (optional) is a type of map of string
  node_meta = {}
  # passing - (optional) is a type of bool
  passing = null
  # tag - (optional) is a type of string
  tag = null
  # wait_for - (optional) is a type of string
  wait_for = null
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

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "near" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "passing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_for" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "consul_service_health" "this" {
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # filter - (optional) is a type of string
  filter = var.filter
  # name - (required) is a type of string
  name = var.name
  # near - (optional) is a type of string
  near = var.near
  # node_meta - (optional) is a type of map of string
  node_meta = var.node_meta
  # passing - (optional) is a type of bool
  passing = var.passing
  # tag - (optional) is a type of string
  tag = var.tag
  # wait_for - (optional) is a type of string
  wait_for = var.wait_for
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.consul_service_health.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.consul_service_health.this.results
}

output "this" {
  value = consul_service_health.this
}
```

[top](#index)