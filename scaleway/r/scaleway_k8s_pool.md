# scaleway_k8s_pool

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/scaleway/r/scaleway_k8s_pool"

  # autohealing - (optional) is a type of bool
  autohealing = null
  # autoscaling - (optional) is a type of bool
  autoscaling = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # container_runtime - (optional) is a type of string
  container_runtime = null
  # kubelet_args - (optional) is a type of map of string
  kubelet_args = {}
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # node_type - (required) is a type of string
  node_type = null
  # placement_group_id - (optional) is a type of string
  placement_group_id = null
  # region - (optional) is a type of string
  region = null
  # size - (required) is a type of number
  size = null
  # tags - (optional) is a type of list of string
  tags = []
  # wait_for_pool_ready - (optional) is a type of bool
  wait_for_pool_ready = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    default = null
  }]

  upgrade_policy = [{
    max_surge       = null
    max_unavailable = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "autohealing" {
  description = "(optional) - Enable the autohealing on the pool"
  type        = bool
  default     = null
}

variable "autoscaling" {
  description = "(optional) - Enable the autoscaling on the pool"
  type        = bool
  default     = null
}

variable "cluster_id" {
  description = "(required) - The ID of the cluster on which this pool will be created"
  type        = string
}

variable "container_runtime" {
  description = "(optional) - Container runtime for the pool"
  type        = string
  default     = null
}

variable "kubelet_args" {
  description = "(optional) - The Kubelet arguments to be used by this pool"
  type        = map(string)
  default     = null
}

variable "max_size" {
  description = "(optional) - Maximum size of the pool"
  type        = number
  default     = null
}

variable "min_size" {
  description = "(optional) - Minimun size of the pool"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of the cluster"
  type        = string
}

variable "node_type" {
  description = "(required) - Server type of the pool servers"
  type        = string
}

variable "placement_group_id" {
  description = "(optional) - ID of the placement group"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "size" {
  description = "(required) - Size of the pool"
  type        = number
}

variable "tags" {
  description = "(optional) - The tags associated with the pool"
  type        = list(string)
  default     = null
}

variable "wait_for_pool_ready" {
  description = "(optional) - Whether to wait for the pool to be ready"
  type        = bool
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}

variable "upgrade_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_surge       = number
      max_unavailable = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_k8s_pool" "this" {
  # autohealing - (optional) is a type of bool
  autohealing = var.autohealing
  # autoscaling - (optional) is a type of bool
  autoscaling = var.autoscaling
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # container_runtime - (optional) is a type of string
  container_runtime = var.container_runtime
  # kubelet_args - (optional) is a type of map of string
  kubelet_args = var.kubelet_args
  # max_size - (optional) is a type of number
  max_size = var.max_size
  # min_size - (optional) is a type of number
  min_size = var.min_size
  # name - (required) is a type of string
  name = var.name
  # node_type - (required) is a type of string
  node_type = var.node_type
  # placement_group_id - (optional) is a type of string
  placement_group_id = var.placement_group_id
  # region - (optional) is a type of string
  region = var.region
  # size - (required) is a type of number
  size = var.size
  # tags - (optional) is a type of list of string
  tags = var.tags
  # wait_for_pool_ready - (optional) is a type of bool
  wait_for_pool_ready = var.wait_for_pool_ready
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

  dynamic "upgrade_policy" {
    for_each = var.upgrade_policy
    content {
      # max_surge - (optional) is a type of number
      max_surge = upgrade_policy.value["max_surge"]
      # max_unavailable - (optional) is a type of number
      max_unavailable = upgrade_policy.value["max_unavailable"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.created_at
}

output "current_size" {
  description = "returns a number"
  value       = scaleway_k8s_pool.this.current_size
}

output "id" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.id
}

output "max_size" {
  description = "returns a number"
  value       = scaleway_k8s_pool.this.max_size
}

output "nodes" {
  description = "returns a list of object"
  value       = scaleway_k8s_pool.this.nodes
}

output "region" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.region
}

output "status" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.updated_at
}

output "version" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.version
}

output "zone" {
  description = "returns a string"
  value       = scaleway_k8s_pool.this.zone
}

output "this" {
  value = scaleway_k8s_pool.this
}
```

[top](#index)