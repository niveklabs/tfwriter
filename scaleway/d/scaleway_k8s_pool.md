# scaleway_k8s_pool

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_k8s_pool" {
  source = "./modules/scaleway/d/scaleway_k8s_pool"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # name - (optional) is a type of string
  name = null
  # pool_id - (optional) is a type of string
  pool_id = null
  # region - (optional) is a type of string
  region = null
  # size - (optional) is a type of number
  size = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional) - The ID of the cluster on which this pool will be created"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the cluster"
  type        = string
  default     = null
}

variable "pool_id" {
  description = "(optional) - The ID of the pool"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional) - Size of the pool"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_k8s_pool" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # name - (optional) is a type of string
  name = var.name
  # pool_id - (optional) is a type of string
  pool_id = var.pool_id
  # region - (optional) is a type of string
  region = var.region
  # size - (optional) is a type of number
  size = var.size
}
```

[top](#index)

### Outputs

```terraform
output "autohealing" {
  description = "returns a bool"
  value       = data.scaleway_k8s_pool.this.autohealing
}

output "autoscaling" {
  description = "returns a bool"
  value       = data.scaleway_k8s_pool.this.autoscaling
}

output "container_runtime" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.container_runtime
}

output "created_at" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.created_at
}

output "current_size" {
  description = "returns a number"
  value       = data.scaleway_k8s_pool.this.current_size
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.id
}

output "kubelet_args" {
  description = "returns a map of string"
  value       = data.scaleway_k8s_pool.this.kubelet_args
}

output "max_size" {
  description = "returns a number"
  value       = data.scaleway_k8s_pool.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = data.scaleway_k8s_pool.this.min_size
}

output "node_type" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.node_type
}

output "nodes" {
  description = "returns a list of object"
  value       = data.scaleway_k8s_pool.this.nodes
}

output "placement_group_id" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.placement_group_id
}

output "status" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.status
}

output "tags" {
  description = "returns a list of string"
  value       = data.scaleway_k8s_pool.this.tags
}

output "updated_at" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.updated_at
}

output "upgrade_policy" {
  description = "returns a list of object"
  value       = data.scaleway_k8s_pool.this.upgrade_policy
}

output "version" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.version
}

output "wait_for_pool_ready" {
  description = "returns a bool"
  value       = data.scaleway_k8s_pool.this.wait_for_pool_ready
}

output "zone" {
  description = "returns a string"
  value       = data.scaleway_k8s_pool.this.zone
}

output "this" {
  value = scaleway_k8s_pool.this
}
```

[top](#index)