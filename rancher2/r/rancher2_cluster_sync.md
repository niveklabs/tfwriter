# rancher2_cluster_sync

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_cluster_sync" {
  source = "./modules/rancher2/r/rancher2_cluster_sync"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # node_pool_ids - (optional) is a type of list of string
  node_pool_ids = []
  # state_confirm - (optional) is a type of number
  state_confirm = null
  # synced - (optional) is a type of bool
  synced = null
  # wait_catalogs - (optional) is a type of bool
  wait_catalogs = null
  # wait_monitoring - (optional) is a type of bool
  wait_monitoring = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - Cluster id to sync"
  type        = string
}

variable "node_pool_ids" {
  description = "(optional) - Cluster node pool ids"
  type        = list(string)
  default     = null
}

variable "state_confirm" {
  description = "(optional) - Wait until active status is confirmed a number of times (wait interval of 5s)"
  type        = number
  default     = null
}

variable "synced" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "wait_catalogs" {
  description = "(optional) - Wait until all catalogs are downloaded and active"
  type        = bool
  default     = null
}

variable "wait_monitoring" {
  description = "(optional) - Wait until monitoring is up and running"
  type        = bool
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_cluster_sync" "this" {
  cluster_id      = var.cluster_id
  node_pool_ids   = var.node_pool_ids
  state_confirm   = var.state_confirm
  synced          = var.synced
  wait_catalogs   = var.wait_catalogs
  wait_monitoring = var.wait_monitoring

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_project_id" {
  description = "returns a string"
  value       = rancher2_cluster_sync.this.default_project_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster_sync.this.id
}

output "kube_config" {
  description = "returns a string"
  value       = rancher2_cluster_sync.this.kube_config
  sensitive   = true
}

output "nodes" {
  description = "returns a list of object"
  value       = rancher2_cluster_sync.this.nodes
}

output "system_project_id" {
  description = "returns a string"
  value       = rancher2_cluster_sync.this.system_project_id
}

output "this" {
  value = rancher2_cluster_sync.this
}
```

[top](#index)