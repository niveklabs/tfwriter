# digitalocean_loadbalancer

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_loadbalancer" {
  source = "./modules/digitalocean/d/digitalocean_loadbalancer"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of the load balancer"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_loadbalancer" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.algorithm
}

output "droplet_ids" {
  description = "returns a set of number"
  value       = data.digitalocean_loadbalancer.this.droplet_ids
}

output "droplet_tag" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.droplet_tag
}

output "enable_backend_keepalive" {
  description = "returns a bool"
  value       = data.digitalocean_loadbalancer.this.enable_backend_keepalive
}

output "enable_proxy_protocol" {
  description = "returns a bool"
  value       = data.digitalocean_loadbalancer.this.enable_proxy_protocol
}

output "forwarding_rule" {
  description = "returns a set of object"
  value       = data.digitalocean_loadbalancer.this.forwarding_rule
}

output "healthcheck" {
  description = "returns a list of object"
  value       = data.digitalocean_loadbalancer.this.healthcheck
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.ip
}

output "redirect_http_to_https" {
  description = "returns a bool"
  value       = data.digitalocean_loadbalancer.this.redirect_http_to_https
}

output "region" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.region
}

output "size" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.size
}

output "status" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.status
}

output "sticky_sessions" {
  description = "returns a list of object"
  value       = data.digitalocean_loadbalancer.this.sticky_sessions
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.urn
}

output "vpc_uuid" {
  description = "returns a string"
  value       = data.digitalocean_loadbalancer.this.vpc_uuid
}

output "this" {
  value = digitalocean_loadbalancer.this
}
```

[top](#index)