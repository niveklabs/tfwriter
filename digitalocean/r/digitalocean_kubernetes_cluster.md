# digitalocean_kubernetes_cluster

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/digitalocean/r/digitalocean_kubernetes_cluster"

  # auto_upgrade - (optional) is a type of bool
  auto_upgrade = null
  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
  # surge_upgrade - (optional) is a type of bool
  surge_upgrade = null
  # tags - (optional) is a type of set of string
  tags = []
  # version - (required) is a type of string
  version = null
  # vpc_uuid - (optional) is a type of string
  vpc_uuid = null

  node_pool = [{
    actual_node_count = null
    auto_scale        = null
    id                = null
    labels            = {}
    max_nodes         = null
    min_nodes         = null
    name              = null
    node_count        = null
    nodes = [{
      created_at = null
      droplet_id = null
      id         = null
      name       = null
      status     = null
      updated_at = null
    }]
    size = null
    tags = []
    taint = [{
      effect = null
      key    = null
      value  = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "surge_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "vpc_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_pool" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      actual_node_count = number
      auto_scale        = bool
      id                = string
      labels            = map(string)
      max_nodes         = number
      min_nodes         = number
      name              = string
      node_count        = number
      nodes = list(object(
        {
          created_at = string
          droplet_id = string
          id         = string
          name       = string
          status     = string
          updated_at = string
        }
      ))
      size = string
      tags = set(string)
      taint = set(object(
        {
          effect = string
          key    = string
          value  = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_kubernetes_cluster" "this" {
  # auto_upgrade - (optional) is a type of bool
  auto_upgrade = var.auto_upgrade
  # name - (required) is a type of string
  name = var.name
  # region - (required) is a type of string
  region = var.region
  # surge_upgrade - (optional) is a type of bool
  surge_upgrade = var.surge_upgrade
  # tags - (optional) is a type of set of string
  tags = var.tags
  # version - (required) is a type of string
  version = var.version
  # vpc_uuid - (optional) is a type of string
  vpc_uuid = var.vpc_uuid

  dynamic "node_pool" {
    for_each = var.node_pool
    content {
      # auto_scale - (optional) is a type of bool
      auto_scale = node_pool.value["auto_scale"]
      # labels - (optional) is a type of map of string
      labels = node_pool.value["labels"]
      # max_nodes - (optional) is a type of number
      max_nodes = node_pool.value["max_nodes"]
      # min_nodes - (optional) is a type of number
      min_nodes = node_pool.value["min_nodes"]
      # name - (required) is a type of string
      name = node_pool.value["name"]
      # node_count - (optional) is a type of number
      node_count = node_pool.value["node_count"]
      # size - (required) is a type of string
      size = node_pool.value["size"]
      # tags - (optional) is a type of set of string
      tags = node_pool.value["tags"]

      dynamic "taint" {
        for_each = node_pool.value.taint
        content {
          # effect - (required) is a type of string
          effect = taint.value["effect"]
          # key - (required) is a type of string
          key = taint.value["key"]
          # value - (required) is a type of string
          value = taint.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_subnet" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.cluster_subnet
}

output "created_at" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.created_at
}

output "endpoint" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.id
}

output "ipv4_address" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.ipv4_address
}

output "kube_config" {
  description = "returns a list of object"
  value       = digitalocean_kubernetes_cluster.this.kube_config
  sensitive   = true
}

output "service_subnet" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.service_subnet
}

output "status" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.updated_at
}

output "vpc_uuid" {
  description = "returns a string"
  value       = digitalocean_kubernetes_cluster.this.vpc_uuid
}

output "this" {
  value = digitalocean_kubernetes_cluster.this
}
```

[top](#index)