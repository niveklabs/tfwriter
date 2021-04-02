# azurerm_kubernetes_cluster

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_kubernetes_cluster" {
  source = "./modules/azurerm/r/azurerm_kubernetes_cluster"

  # api_server_authorized_ip_ranges - (optional) is a type of set of string
  api_server_authorized_ip_ranges = []
  # automatic_channel_upgrade - (optional) is a type of string
  automatic_channel_upgrade = null
  # disk_encryption_set_id - (optional) is a type of string
  disk_encryption_set_id = null
  # dns_prefix - (required) is a type of string
  dns_prefix = null
  # enable_pod_security_policy - (optional) is a type of bool
  enable_pod_security_policy = null
  # kubernetes_version - (optional) is a type of string
  kubernetes_version = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # node_resource_group - (optional) is a type of string
  node_resource_group = null
  # private_cluster_enabled - (optional) is a type of bool
  private_cluster_enabled = null
  # private_dns_zone_id - (optional) is a type of string
  private_dns_zone_id = null
  # private_link_enabled - (optional) is a type of bool
  private_link_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_tier - (optional) is a type of string
  sku_tier = null
  # tags - (optional) is a type of map of string
  tags = {}

  addon_profile = [{
    aci_connector_linux = [{
      enabled     = null
      subnet_name = null
    }]
    azure_policy = [{
      enabled = null
    }]
    http_application_routing = [{
      enabled                            = null
      http_application_routing_zone_name = null
    }]
    kube_dashboard = [{
      enabled = null
    }]
    oms_agent = [{
      enabled                    = null
      log_analytics_workspace_id = null
      oms_agent_identity = [{
        client_id                 = null
        object_id                 = null
        user_assigned_identity_id = null
      }]
    }]
  }]

  auto_scaler_profile = [{
    balance_similar_node_groups      = null
    expander                         = null
    max_graceful_termination_sec     = null
    new_pod_scale_up_delay           = null
    scale_down_delay_after_add       = null
    scale_down_delay_after_delete    = null
    scale_down_delay_after_failure   = null
    scale_down_unneeded              = null
    scale_down_unready               = null
    scale_down_utilization_threshold = null
    scan_interval                    = null
    skip_nodes_with_local_storage    = null
    skip_nodes_with_system_pods      = null
  }]

  default_node_pool = [{
    availability_zones           = []
    enable_auto_scaling          = null
    enable_host_encryption       = null
    enable_node_public_ip        = null
    max_count                    = null
    max_pods                     = null
    min_count                    = null
    name                         = null
    node_count                   = null
    node_labels                  = {}
    node_taints                  = []
    only_critical_addons_enabled = null
    orchestrator_version         = null
    os_disk_size_gb              = null
    os_disk_type                 = null
    proximity_placement_group_id = null
    tags                         = {}
    type                         = null
    upgrade_settings = [{
      max_surge = null
    }]
    vm_size        = null
    vnet_subnet_id = null
  }]

  identity = [{
    principal_id              = null
    tenant_id                 = null
    type                      = null
    user_assigned_identity_id = null
  }]

  linux_profile = [{
    admin_username = null
    ssh_key = [{
      key_data = null
    }]
  }]

  network_profile = [{
    dns_service_ip     = null
    docker_bridge_cidr = null
    load_balancer_profile = [{
      effective_outbound_ips    = []
      idle_timeout_in_minutes   = null
      managed_outbound_ip_count = null
      outbound_ip_address_ids   = []
      outbound_ip_prefix_ids    = []
      outbound_ports_allocated  = null
    }]
    load_balancer_sku = null
    network_mode      = null
    network_plugin    = null
    network_policy    = null
    outbound_type     = null
    pod_cidr          = null
    service_cidr      = null
  }]

  role_based_access_control = [{
    azure_active_directory = [{
      admin_group_object_ids = []
      client_app_id          = null
      managed                = null
      server_app_id          = null
      server_app_secret      = null
      tenant_id              = null
    }]
    enabled = null
  }]

  service_principal = [{
    client_id     = null
    client_secret = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  windows_profile = [{
    admin_password = null
    admin_username = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_server_authorized_ip_ranges" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "automatic_channel_upgrade" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_encryption_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_prefix" {
  description = "(required)"
  type        = string
}

variable "enable_pod_security_policy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kubernetes_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_resource_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_cluster_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "private_dns_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_link_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "addon_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aci_connector_linux = list(object(
        {
          enabled     = bool
          subnet_name = string
        }
      ))
      azure_policy = list(object(
        {
          enabled = bool
        }
      ))
      http_application_routing = list(object(
        {
          enabled                            = bool
          http_application_routing_zone_name = string
        }
      ))
      kube_dashboard = list(object(
        {
          enabled = bool
        }
      ))
      oms_agent = list(object(
        {
          enabled                    = bool
          log_analytics_workspace_id = string
          oms_agent_identity = list(object(
            {
              client_id                 = string
              object_id                 = string
              user_assigned_identity_id = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "auto_scaler_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      balance_similar_node_groups      = bool
      expander                         = string
      max_graceful_termination_sec     = string
      new_pod_scale_up_delay           = string
      scale_down_delay_after_add       = string
      scale_down_delay_after_delete    = string
      scale_down_delay_after_failure   = string
      scale_down_unneeded              = string
      scale_down_unready               = string
      scale_down_utilization_threshold = string
      scan_interval                    = string
      skip_nodes_with_local_storage    = bool
      skip_nodes_with_system_pods      = bool
    }
  ))
  default = []
}

variable "default_node_pool" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      availability_zones           = list(string)
      enable_auto_scaling          = bool
      enable_host_encryption       = bool
      enable_node_public_ip        = bool
      max_count                    = number
      max_pods                     = number
      min_count                    = number
      name                         = string
      node_count                   = number
      node_labels                  = map(string)
      node_taints                  = list(string)
      only_critical_addons_enabled = bool
      orchestrator_version         = string
      os_disk_size_gb              = number
      os_disk_type                 = string
      proximity_placement_group_id = string
      tags                         = map(string)
      type                         = string
      upgrade_settings = list(object(
        {
          max_surge = string
        }
      ))
      vm_size        = string
      vnet_subnet_id = string
    }
  ))
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id              = string
      tenant_id                 = string
      type                      = string
      user_assigned_identity_id = string
    }
  ))
  default = []
}

variable "linux_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin_username = string
      ssh_key = list(object(
        {
          key_data = string
        }
      ))
    }
  ))
  default = []
}

variable "network_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dns_service_ip     = string
      docker_bridge_cidr = string
      load_balancer_profile = list(object(
        {
          effective_outbound_ips    = set(string)
          idle_timeout_in_minutes   = number
          managed_outbound_ip_count = number
          outbound_ip_address_ids   = set(string)
          outbound_ip_prefix_ids    = set(string)
          outbound_ports_allocated  = number
        }
      ))
      load_balancer_sku = string
      network_mode      = string
      network_plugin    = string
      network_policy    = string
      outbound_type     = string
      pod_cidr          = string
      service_cidr      = string
    }
  ))
  default = []
}

variable "role_based_access_control" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      azure_active_directory = list(object(
        {
          admin_group_object_ids = set(string)
          client_app_id          = string
          managed                = bool
          server_app_id          = string
          server_app_secret      = string
          tenant_id              = string
        }
      ))
      enabled = bool
    }
  ))
  default = []
}

variable "service_principal" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_id     = string
      client_secret = string
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
      read   = string
      update = string
    }
  ))
  default = []
}

variable "windows_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin_password = string
      admin_username = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_kubernetes_cluster" "this" {
  api_server_authorized_ip_ranges = var.api_server_authorized_ip_ranges
  automatic_channel_upgrade       = var.automatic_channel_upgrade
  disk_encryption_set_id          = var.disk_encryption_set_id
  dns_prefix                      = var.dns_prefix
  enable_pod_security_policy      = var.enable_pod_security_policy
  kubernetes_version              = var.kubernetes_version
  location                        = var.location
  name                            = var.name
  node_resource_group             = var.node_resource_group
  private_cluster_enabled         = var.private_cluster_enabled
  private_dns_zone_id             = var.private_dns_zone_id
  private_link_enabled            = var.private_link_enabled
  resource_group_name             = var.resource_group_name
  sku_tier                        = var.sku_tier
  tags                            = var.tags

  dynamic "addon_profile" {
    for_each = var.addon_profile
    content {

      dynamic "aci_connector_linux" {
        for_each = addon_profile.value.aci_connector_linux
        content {
          enabled     = aci_connector_linux.value["enabled"]
          subnet_name = aci_connector_linux.value["subnet_name"]
        }
      }

      dynamic "azure_policy" {
        for_each = addon_profile.value.azure_policy
        content {
          enabled = azure_policy.value["enabled"]
        }
      }

      dynamic "http_application_routing" {
        for_each = addon_profile.value.http_application_routing
        content {
          enabled = http_application_routing.value["enabled"]
        }
      }

      dynamic "kube_dashboard" {
        for_each = addon_profile.value.kube_dashboard
        content {
          enabled = kube_dashboard.value["enabled"]
        }
      }

      dynamic "oms_agent" {
        for_each = addon_profile.value.oms_agent
        content {
          enabled                    = oms_agent.value["enabled"]
          log_analytics_workspace_id = oms_agent.value["log_analytics_workspace_id"]
        }
      }

    }
  }

  dynamic "auto_scaler_profile" {
    for_each = var.auto_scaler_profile
    content {
      balance_similar_node_groups      = auto_scaler_profile.value["balance_similar_node_groups"]
      expander                         = auto_scaler_profile.value["expander"]
      max_graceful_termination_sec     = auto_scaler_profile.value["max_graceful_termination_sec"]
      new_pod_scale_up_delay           = auto_scaler_profile.value["new_pod_scale_up_delay"]
      scale_down_delay_after_add       = auto_scaler_profile.value["scale_down_delay_after_add"]
      scale_down_delay_after_delete    = auto_scaler_profile.value["scale_down_delay_after_delete"]
      scale_down_delay_after_failure   = auto_scaler_profile.value["scale_down_delay_after_failure"]
      scale_down_unneeded              = auto_scaler_profile.value["scale_down_unneeded"]
      scale_down_unready               = auto_scaler_profile.value["scale_down_unready"]
      scale_down_utilization_threshold = auto_scaler_profile.value["scale_down_utilization_threshold"]
      scan_interval                    = auto_scaler_profile.value["scan_interval"]
      skip_nodes_with_local_storage    = auto_scaler_profile.value["skip_nodes_with_local_storage"]
      skip_nodes_with_system_pods      = auto_scaler_profile.value["skip_nodes_with_system_pods"]
    }
  }

  dynamic "default_node_pool" {
    for_each = var.default_node_pool
    content {
      availability_zones           = default_node_pool.value["availability_zones"]
      enable_auto_scaling          = default_node_pool.value["enable_auto_scaling"]
      enable_host_encryption       = default_node_pool.value["enable_host_encryption"]
      enable_node_public_ip        = default_node_pool.value["enable_node_public_ip"]
      max_count                    = default_node_pool.value["max_count"]
      max_pods                     = default_node_pool.value["max_pods"]
      min_count                    = default_node_pool.value["min_count"]
      name                         = default_node_pool.value["name"]
      node_count                   = default_node_pool.value["node_count"]
      node_labels                  = default_node_pool.value["node_labels"]
      node_taints                  = default_node_pool.value["node_taints"]
      only_critical_addons_enabled = default_node_pool.value["only_critical_addons_enabled"]
      orchestrator_version         = default_node_pool.value["orchestrator_version"]
      os_disk_size_gb              = default_node_pool.value["os_disk_size_gb"]
      os_disk_type                 = default_node_pool.value["os_disk_type"]
      proximity_placement_group_id = default_node_pool.value["proximity_placement_group_id"]
      tags                         = default_node_pool.value["tags"]
      type                         = default_node_pool.value["type"]
      vm_size                      = default_node_pool.value["vm_size"]
      vnet_subnet_id               = default_node_pool.value["vnet_subnet_id"]

      dynamic "upgrade_settings" {
        for_each = default_node_pool.value.upgrade_settings
        content {
          max_surge = upgrade_settings.value["max_surge"]
        }
      }

    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      type                      = identity.value["type"]
      user_assigned_identity_id = identity.value["user_assigned_identity_id"]
    }
  }

  dynamic "linux_profile" {
    for_each = var.linux_profile
    content {
      admin_username = linux_profile.value["admin_username"]

      dynamic "ssh_key" {
        for_each = linux_profile.value.ssh_key
        content {
          key_data = ssh_key.value["key_data"]
        }
      }

    }
  }

  dynamic "network_profile" {
    for_each = var.network_profile
    content {
      dns_service_ip     = network_profile.value["dns_service_ip"]
      docker_bridge_cidr = network_profile.value["docker_bridge_cidr"]
      load_balancer_sku  = network_profile.value["load_balancer_sku"]
      network_mode       = network_profile.value["network_mode"]
      network_plugin     = network_profile.value["network_plugin"]
      network_policy     = network_profile.value["network_policy"]
      outbound_type      = network_profile.value["outbound_type"]
      pod_cidr           = network_profile.value["pod_cidr"]
      service_cidr       = network_profile.value["service_cidr"]

      dynamic "load_balancer_profile" {
        for_each = network_profile.value.load_balancer_profile
        content {
          idle_timeout_in_minutes   = load_balancer_profile.value["idle_timeout_in_minutes"]
          managed_outbound_ip_count = load_balancer_profile.value["managed_outbound_ip_count"]
          outbound_ip_address_ids   = load_balancer_profile.value["outbound_ip_address_ids"]
          outbound_ip_prefix_ids    = load_balancer_profile.value["outbound_ip_prefix_ids"]
          outbound_ports_allocated  = load_balancer_profile.value["outbound_ports_allocated"]
        }
      }

    }
  }

  dynamic "role_based_access_control" {
    for_each = var.role_based_access_control
    content {
      enabled = role_based_access_control.value["enabled"]

      dynamic "azure_active_directory" {
        for_each = role_based_access_control.value.azure_active_directory
        content {
          admin_group_object_ids = azure_active_directory.value["admin_group_object_ids"]
          client_app_id          = azure_active_directory.value["client_app_id"]
          managed                = azure_active_directory.value["managed"]
          server_app_id          = azure_active_directory.value["server_app_id"]
          server_app_secret      = azure_active_directory.value["server_app_secret"]
          tenant_id              = azure_active_directory.value["tenant_id"]
        }
      }

    }
  }

  dynamic "service_principal" {
    for_each = var.service_principal
    content {
      client_id     = service_principal.value["client_id"]
      client_secret = service_principal.value["client_secret"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

  dynamic "windows_profile" {
    for_each = var.windows_profile
    content {
      admin_password = windows_profile.value["admin_password"]
      admin_username = windows_profile.value["admin_username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fqdn" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.id
}

output "kube_admin_config" {
  description = "returns a list of object"
  value       = azurerm_kubernetes_cluster.this.kube_admin_config
}

output "kube_admin_config_raw" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.kube_admin_config_raw
  sensitive   = true
}

output "kube_config" {
  description = "returns a list of object"
  value       = azurerm_kubernetes_cluster.this.kube_config
}

output "kube_config_raw" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.kube_config_raw
  sensitive   = true
}

output "kubelet_identity" {
  description = "returns a list of object"
  value       = azurerm_kubernetes_cluster.this.kubelet_identity
}

output "kubernetes_version" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.kubernetes_version
}

output "node_resource_group" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.node_resource_group
}

output "private_cluster_enabled" {
  description = "returns a bool"
  value       = azurerm_kubernetes_cluster.this.private_cluster_enabled
}

output "private_dns_zone_id" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.private_dns_zone_id
}

output "private_fqdn" {
  description = "returns a string"
  value       = azurerm_kubernetes_cluster.this.private_fqdn
}

output "private_link_enabled" {
  description = "returns a bool"
  value       = azurerm_kubernetes_cluster.this.private_link_enabled
}

output "this" {
  value = azurerm_kubernetes_cluster.this
}
```

[top](#index)