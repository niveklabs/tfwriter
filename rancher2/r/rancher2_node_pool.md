# rancher2_node_pool

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
module "rancher2_node_pool" {
  source = "./modules/rancher2/r/rancher2_node_pool"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # control_plane - (optional) is a type of bool
  control_plane = null
  # delete_not_ready_after_secs - (optional) is a type of number
  delete_not_ready_after_secs = null
  # etcd - (optional) is a type of bool
  etcd = null
  # hostname_prefix - (required) is a type of string
  hostname_prefix = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # node_template_id - (required) is a type of string
  node_template_id = null
  # quantity - (optional) is a type of number
  quantity = null
  # worker - (optional) is a type of bool
  worker = null

  node_taints = [{
    effect     = null
    key        = null
    time_added = null
    value      = null
  }]

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
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "control_plane" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "delete_not_ready_after_secs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "etcd" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hostname_prefix" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_template_id" {
  description = "(required)"
  type        = string
}

variable "quantity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "node_taints" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      effect     = string
      key        = string
      time_added = string
      value      = string
    }
  ))
  default = []
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
resource "rancher2_node_pool" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # control_plane - (optional) is a type of bool
  control_plane = var.control_plane
  # delete_not_ready_after_secs - (optional) is a type of number
  delete_not_ready_after_secs = var.delete_not_ready_after_secs
  # etcd - (optional) is a type of bool
  etcd = var.etcd
  # hostname_prefix - (required) is a type of string
  hostname_prefix = var.hostname_prefix
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # node_template_id - (required) is a type of string
  node_template_id = var.node_template_id
  # quantity - (optional) is a type of number
  quantity = var.quantity
  # worker - (optional) is a type of bool
  worker = var.worker

  dynamic "node_taints" {
    for_each = var.node_taints
    content {
      # effect - (optional) is a type of string
      effect = node_taints.value["effect"]
      # key - (required) is a type of string
      key = node_taints.value["key"]
      # time_added - (optional) is a type of string
      time_added = node_taints.value["time_added"]
      # value - (required) is a type of string
      value = node_taints.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_node_pool.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_node_pool.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_node_pool.this.labels
}

output "this" {
  value = rancher2_node_pool.this
}
```

[top](#index)