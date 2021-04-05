# nutanix_karbon_cluster

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_karbon_cluster" {
  source = "./modules/nutanix/d/nutanix_karbon_cluster"

  # karbon_cluster_id - (optional) is a type of string
  karbon_cluster_id = null
  # karbon_cluster_name - (optional) is a type of string
  karbon_cluster_name = null
}
```

[top](#index)

### Variables

```terraform
variable "karbon_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "karbon_cluster_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_karbon_cluster" "this" {
  karbon_cluster_id   = var.karbon_cluster_id
  karbon_cluster_name = var.karbon_cluster_name
}
```

[top](#index)

### Outputs

```terraform
output "deployment_type" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.deployment_type
}

output "etcd_node_pool" {
  description = "returns a list of object"
  value       = data.nutanix_karbon_cluster.this.etcd_node_pool
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.id
}

output "kubeapi_server_ipv4_address" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.kubeapi_server_ipv4_address
}

output "master_node_pool" {
  description = "returns a list of object"
  value       = data.nutanix_karbon_cluster.this.master_node_pool
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.name
}

output "status" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.status
}

output "uuid" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.uuid
}

output "version" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster.this.version
}

output "worker_node_pool" {
  description = "returns a list of object"
  value       = data.nutanix_karbon_cluster.this.worker_node_pool
}

output "this" {
  value = nutanix_karbon_cluster.this
}
```

[top](#index)