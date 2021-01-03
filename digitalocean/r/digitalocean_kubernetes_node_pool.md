# digitalocean_kubernetes_node_pool

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
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_kubernetes_node_pool" {
  source = "./modules/digitalocean/r/digitalocean_kubernetes_node_pool"

  # auto_scale - (optional) is a type of bool
  auto_scale = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # max_nodes - (optional) is a type of number
  max_nodes = null
  # min_nodes - (optional) is a type of number
  min_nodes = null
  # name - (required) is a type of string
  name = null
  # node_count - (optional) is a type of number
  node_count = null
  # size - (required) is a type of string
  size = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "auto_scale" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "max_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "size" {
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

### Resource

```terraform
resource "digitalocean_kubernetes_node_pool" "this" {
  auto_scale = var.auto_scale
  cluster_id = var.cluster_id
  labels     = var.labels
  max_nodes  = var.max_nodes
  min_nodes  = var.min_nodes
  name       = var.name
  node_count = var.node_count
  size       = var.size
  tags       = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "actual_node_count" {
  description = "returns a number"
  value       = digitalocean_kubernetes_node_pool.this.actual_node_count
}

output "id" {
  description = "returns a string"
  value       = digitalocean_kubernetes_node_pool.this.id
}

output "nodes" {
  description = "returns a list of object"
  value       = digitalocean_kubernetes_node_pool.this.nodes
}

output "this" {
  value = digitalocean_kubernetes_node_pool.this
}
```

[top](#index)