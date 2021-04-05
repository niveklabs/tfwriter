# profitbricks_k8s_node_pool

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_k8s_node_pool" {
  source = "./modules/profitbricks/d/profitbricks_k8s_node_pool"

  # k8s_cluster_id - (required) is a type of string
  k8s_cluster_id = null
  # name - (optional) is a type of string
  name = null
  # public_ips - (optional) is a type of list of string
  public_ips = []

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "k8s_cluster_id" {
  description = "(required) - The UUID of an existing kubernetes cluster"
  type        = string
}

variable "name" {
  description = "(optional) - The desired name for the node pool"
  type        = string
  default     = null
}

variable "public_ips" {
  description = "(optional) - A list of fixed IPs"
  type        = list(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "profitbricks_k8s_node_pool" "this" {
  k8s_cluster_id = var.k8s_cluster_id
  name           = var.name
  public_ips     = var.public_ips

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.profitbricks_k8s_node_pool.this.annotations
}

output "auto_scaling" {
  description = "returns a list of object"
  value       = data.profitbricks_k8s_node_pool.this.auto_scaling
}

output "availability_zone" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.availability_zone
}

output "available_upgrade_versions" {
  description = "returns a list of string"
  value       = data.profitbricks_k8s_node_pool.this.available_upgrade_versions
}

output "cores_count" {
  description = "returns a number"
  value       = data.profitbricks_k8s_node_pool.this.cores_count
}

output "cpu_family" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.cpu_family
}

output "datacenter_id" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.datacenter_id
}

output "id" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.id
}

output "k8s_version" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.k8s_version
}

output "labels" {
  description = "returns a map of string"
  value       = data.profitbricks_k8s_node_pool.this.labels
}

output "lans" {
  description = "returns a list of number"
  value       = data.profitbricks_k8s_node_pool.this.lans
}

output "maintenance_window" {
  description = "returns a list of object"
  value       = data.profitbricks_k8s_node_pool.this.maintenance_window
}

output "node_count" {
  description = "returns a number"
  value       = data.profitbricks_k8s_node_pool.this.node_count
}

output "ram_size" {
  description = "returns a number"
  value       = data.profitbricks_k8s_node_pool.this.ram_size
}

output "state" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.state
}

output "storage_size" {
  description = "returns a number"
  value       = data.profitbricks_k8s_node_pool.this.storage_size
}

output "storage_type" {
  description = "returns a string"
  value       = data.profitbricks_k8s_node_pool.this.storage_type
}

output "this" {
  value = profitbricks_k8s_node_pool.this
}
```

[top](#index)