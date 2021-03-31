# digitalocean_kubernetes_cluster

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
module "digitalocean_kubernetes_cluster" {
  source = "./modules/digitalocean/d/digitalocean_kubernetes_cluster"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_kubernetes_cluster" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "auto_upgrade" {
  description = "returns a bool"
  value       = data.digitalocean_kubernetes_cluster.this.auto_upgrade
}

output "cluster_subnet" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.cluster_subnet
}

output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.created_at
}

output "endpoint" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.id
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.ipv4_address
}

output "kube_config" {
  description = "returns a list of object"
  value       = data.digitalocean_kubernetes_cluster.this.kube_config
  sensitive   = true
}

output "node_pool" {
  description = "returns a list of object"
  value       = data.digitalocean_kubernetes_cluster.this.node_pool
}

output "region" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.region
}

output "service_subnet" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.service_subnet
}

output "status" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.status
}

output "surge_upgrade" {
  description = "returns a bool"
  value       = data.digitalocean_kubernetes_cluster.this.surge_upgrade
}

output "updated_at" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.updated_at
}

output "version" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.version
}

output "vpc_uuid" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_cluster.this.vpc_uuid
}

output "this" {
  value = digitalocean_kubernetes_cluster.this
}
```

[top](#index)