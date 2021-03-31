# azurerm_kubernetes_cluster

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_kubernetes_cluster" {
  source = "./modules/azurerm/d/azurerm_kubernetes_cluster"

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
data "azurerm_kubernetes_cluster" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "addon_profile" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.addon_profile
}

output "agent_pool_profile" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.agent_pool_profile
}

output "api_server_authorized_ip_ranges" {
  description = "returns a set of string"
  value       = data.azurerm_kubernetes_cluster.this.api_server_authorized_ip_ranges
}

output "disk_encryption_set_id" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.disk_encryption_set_id
}

output "dns_prefix" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.dns_prefix
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.identity
}

output "kube_admin_config" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.kube_admin_config
}

output "kube_admin_config_raw" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.kube_admin_config_raw
  sensitive   = true
}

output "kube_config" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.kube_config
}

output "kube_config_raw" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.kube_config_raw
  sensitive   = true
}

output "kubelet_identity" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.kubelet_identity
}

output "kubernetes_version" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.kubernetes_version
}

output "linux_profile" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.linux_profile
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.location
}

output "network_profile" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.network_profile
}

output "node_resource_group" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.node_resource_group
}

output "private_cluster_enabled" {
  description = "returns a bool"
  value       = data.azurerm_kubernetes_cluster.this.private_cluster_enabled
}

output "private_fqdn" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_cluster.this.private_fqdn
}

output "private_link_enabled" {
  description = "returns a bool"
  value       = data.azurerm_kubernetes_cluster.this.private_link_enabled
}

output "role_based_access_control" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.role_based_access_control
}

output "service_principal" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.service_principal
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_kubernetes_cluster.this.tags
}

output "windows_profile" {
  description = "returns a list of object"
  value       = data.azurerm_kubernetes_cluster.this.windows_profile
}

output "this" {
  value = azurerm_kubernetes_cluster.this
}
```

[top](#index)