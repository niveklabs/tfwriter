# gridscale_loadbalancer

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_loadbalancer" {
  source = "./modules/gridscale/d/gridscale_loadbalancer"

  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_loadbalancer" "this" {
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.algorithm
}

output "backend_server" {
  description = "returns a set of object"
  value       = data.gridscale_loadbalancer.this.backend_server
}

output "forwarding_rule" {
  description = "returns a set of object"
  value       = data.gridscale_loadbalancer.this.forwarding_rule
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_loadbalancer.this.labels
}

output "listen_ipv4_uuid" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.listen_ipv4_uuid
}

output "listen_ipv6_uuid" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.listen_ipv6_uuid
}

output "location_uuid" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.location_uuid
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.name
}

output "redirect_http_to_https" {
  description = "returns a bool"
  value       = data.gridscale_loadbalancer.this.redirect_http_to_https
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_loadbalancer.this.status
}

output "this" {
  value = gridscale_loadbalancer.this
}
```

[top](#index)