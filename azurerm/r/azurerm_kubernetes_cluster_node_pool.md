# azurerm_kubernetes_cluster_node_pool

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_kubernetes_cluster_node_pool" {
  source = "./modules/azurerm/r/azurerm_kubernetes_cluster_node_pool"

  # availability_zones - (optional) is a type of list of string
  availability_zones = []
  # enable_auto_scaling - (optional) is a type of bool
  enable_auto_scaling = null
  # enable_host_encryption - (optional) is a type of bool
  enable_host_encryption = null
  # enable_node_public_ip - (optional) is a type of bool
  enable_node_public_ip = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # kubernetes_cluster_id - (required) is a type of string
  kubernetes_cluster_id = null
  # max_count - (optional) is a type of number
  max_count = null
  # max_pods - (optional) is a type of number
  max_pods = null
  # min_count - (optional) is a type of number
  min_count = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # node_count - (optional) is a type of number
  node_count = null
  # node_labels - (optional) is a type of map of string
  node_labels = {}
  # node_taints - (optional) is a type of list of string
  node_taints = []
  # orchestrator_version - (optional) is a type of string
  orchestrator_version = null
  # os_disk_size_gb - (optional) is a type of number
  os_disk_size_gb = null
  # os_disk_type - (optional) is a type of string
  os_disk_type = null
  # os_type - (optional) is a type of string
  os_type = null
  # priority - (optional) is a type of string
  priority = null
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = null
  # spot_max_price - (optional) is a type of number
  spot_max_price = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vm_size - (required) is a type of string
  vm_size = null
  # vnet_subnet_id - (optional) is a type of string
  vnet_subnet_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  upgrade_settings = [{
    max_surge = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "enable_auto_scaling" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_host_encryption" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_node_public_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "eviction_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kubernetes_cluster_id" {
  description = "(required)"
  type        = string
}

variable "max_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_pods" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
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

variable "node_labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "node_taints" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "orchestrator_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_disk_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "os_disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proximity_placement_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_max_price" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vm_size" {
  description = "(required)"
  type        = string
}

variable "vnet_subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}

variable "upgrade_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_surge = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_kubernetes_cluster_node_pool" "this" {
  availability_zones           = var.availability_zones
  enable_auto_scaling          = var.enable_auto_scaling
  enable_host_encryption       = var.enable_host_encryption
  enable_node_public_ip        = var.enable_node_public_ip
  eviction_policy              = var.eviction_policy
  kubernetes_cluster_id        = var.kubernetes_cluster_id
  max_count                    = var.max_count
  max_pods                     = var.max_pods
  min_count                    = var.min_count
  mode                         = var.mode
  name                         = var.name
  node_count                   = var.node_count
  node_labels                  = var.node_labels
  node_taints                  = var.node_taints
  orchestrator_version         = var.orchestrator_version
  os_disk_size_gb              = var.os_disk_size_gb
  os_disk_type                 = var.os_disk_type
  os_type                      = var.os_type
  priority                     = var.priority
  proximity_placement_group_id = var.proximity_placement_group_id
  spot_max_price               = var.spot_max_price
  tags                         = var.tags
  vm_size                      = var.vm_size
  vnet_subnet_id               = var.vnet_subnet_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

  dynamic "upgrade_settings" {
    for_each = var.upgrade_settings
    content {
      max_surge = upgrade_settings.value["max_surge"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster_node_pool.this.id
}

output "max_pods" {
  description = "returns a number"
  value       = azurerm_kubernetes_cluster_node_pool.this.max_pods
}

output "node_count" {
  description = "returns a number"
  value       = azurerm_kubernetes_cluster_node_pool.this.node_count
}

output "orchestrator_version" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster_node_pool.this.orchestrator_version
}

output "os_disk_size_gb" {
  description = "returns a number"
  value       = azurerm_kubernetes_cluster_node_pool.this.os_disk_size_gb
}

output "this" {
  value = azurerm_kubernetes_cluster_node_pool.this
}
```

[top](#index)