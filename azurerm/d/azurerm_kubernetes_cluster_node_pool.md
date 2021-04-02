# azurerm_kubernetes_cluster_node_pool

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_kubernetes_cluster_node_pool" {
  source = "./modules/azurerm/d/azurerm_kubernetes_cluster_node_pool"

  # kubernetes_cluster_name - (required) is a type of string
  kubernetes_cluster_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "kubernetes_cluster_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_kubernetes_cluster_node_pool" "this" {
  kubernetes_cluster_name = var.kubernetes_cluster_name
  name                    = var.name
  resource_group_name     = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_zones" {
  description = "returns a list of string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.availability_zones
}

output "enable_auto_scaling" {
  description = "returns a bool"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.enable_auto_scaling
}

output "enable_node_public_ip" {
  description = "returns a bool"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.enable_node_public_ip
}

output "eviction_policy" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.eviction_policy
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.id
}

output "max_count" {
  description = "returns a number"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.max_count
}

output "max_pods" {
  description = "returns a number"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.max_pods
}

output "min_count" {
  description = "returns a number"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.min_count
}

output "mode" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.mode
}

output "node_count" {
  description = "returns a number"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.node_count
}

output "node_labels" {
  description = "returns a map of string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.node_labels
}

output "node_taints" {
  description = "returns a list of string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.node_taints
}

output "orchestrator_version" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.orchestrator_version
}

output "os_disk_size_gb" {
  description = "returns a number"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.os_disk_size_gb
}

output "os_disk_type" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.os_disk_type
}

output "os_type" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.os_type
}

output "priority" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.priority
}

output "proximity_placement_group_id" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.proximity_placement_group_id
}

output "spot_max_price" {
  description = "returns a number"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.spot_max_price
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.tags
}

output "upgrade_settings" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.upgrade_settings
}

output "vm_size" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.vm_size
}

output "vnet_subnet_id" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster_node_pool.this.vnet_subnet_id
}

output "this" {
  value = azurerm_kubernetes_cluster_node_pool.this
}
```

[top](#index)