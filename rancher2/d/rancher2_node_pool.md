# rancher2_node_pool

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/rancher2/d/rancher2_node_pool"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null
  # node_template_id - (optional) is a type of string
  node_template_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_template_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_node_pool" "this" {
  cluster_id       = var.cluster_id
  name             = var.name
  node_template_id = var.node_template_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_node_pool.this.annotations
}

output "control_plane" {
  description = "returns a bool"
  value       = data.rancher2_node_pool.this.control_plane
}

output "delete_not_ready_after_secs" {
  description = "returns a number"
  value       = data.rancher2_node_pool.this.delete_not_ready_after_secs
}

output "etcd" {
  description = "returns a bool"
  value       = data.rancher2_node_pool.this.etcd
}

output "hostname_prefix" {
  description = "returns a string"
  value       = data.rancher2_node_pool.this.hostname_prefix
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_node_pool.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_node_pool.this.labels
}

output "node_taints" {
  description = "returns a list of object"
  value       = data.rancher2_node_pool.this.node_taints
}

output "node_template_id" {
  description = "returns a string"
  value       = data.rancher2_node_pool.this.node_template_id
}

output "quantity" {
  description = "returns a number"
  value       = data.rancher2_node_pool.this.quantity
}

output "worker" {
  description = "returns a bool"
  value       = data.rancher2_node_pool.this.worker
}

output "this" {
  value = rancher2_node_pool.this
}
```

[top](#index)