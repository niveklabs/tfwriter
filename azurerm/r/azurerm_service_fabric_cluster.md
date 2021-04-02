# azurerm_service_fabric_cluster

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
module "azurerm_service_fabric_cluster" {
  source = "./modules/azurerm/r/azurerm_service_fabric_cluster"

  # add_on_features - (optional) is a type of set of string
  add_on_features = []
  # cluster_code_version - (optional) is a type of string
  cluster_code_version = null
  # location - (required) is a type of string
  location = null
  # management_endpoint - (required) is a type of string
  management_endpoint = null
  # name - (required) is a type of string
  name = null
  # reliability_level - (required) is a type of string
  reliability_level = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # upgrade_mode - (required) is a type of string
  upgrade_mode = null
  # vm_image - (required) is a type of string
  vm_image = null

  azure_active_directory = [{
    client_application_id  = null
    cluster_application_id = null
    tenant_id              = null
  }]

  certificate = [{
    thumbprint           = null
    thumbprint_secondary = null
    x509_store_name      = null
  }]

  certificate_common_names = [{
    common_names = [{
      certificate_common_name       = null
      certificate_issuer_thumbprint = null
    }]
    x509_store_name = null
  }]

  client_certificate_common_name = [{
    common_name       = null
    is_admin          = null
    issuer_thumbprint = null
  }]

  client_certificate_thumbprint = [{
    is_admin   = null
    thumbprint = null
  }]

  diagnostics_config = [{
    blob_endpoint              = null
    protected_account_key_name = null
    queue_endpoint             = null
    storage_account_name       = null
    table_endpoint             = null
  }]

  fabric_settings = [{
    name       = null
    parameters = {}
  }]

  node_type = [{
    application_ports = [{
      end_port   = null
      start_port = null
    }]
    capacities           = {}
    client_endpoint_port = null
    durability_level     = null
    ephemeral_ports = [{
      end_port   = null
      start_port = null
    }]
    http_endpoint_port          = null
    instance_count              = null
    is_primary                  = null
    name                        = null
    placement_properties        = {}
    reverse_proxy_endpoint_port = null
  }]

  reverse_proxy_certificate = [{
    thumbprint           = null
    thumbprint_secondary = null
    x509_store_name      = null
  }]

  reverse_proxy_certificate_common_names = [{
    common_names = [{
      certificate_common_name       = null
      certificate_issuer_thumbprint = null
    }]
    x509_store_name = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  upgrade_policy = [{
    delta_health_policy = [{
      max_delta_unhealthy_applications_percent         = null
      max_delta_unhealthy_nodes_percent                = null
      max_upgrade_domain_delta_unhealthy_nodes_percent = null
    }]
    force_restart_enabled        = null
    health_check_retry_timeout   = null
    health_check_stable_duration = null
    health_check_wait_duration   = null
    health_policy = [{
      max_unhealthy_applications_percent = null
      max_unhealthy_nodes_percent        = null
    }]
    upgrade_domain_timeout            = null
    upgrade_replica_set_check_timeout = null
    upgrade_timeout                   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "add_on_features" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cluster_code_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "management_endpoint" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "reliability_level" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "upgrade_mode" {
  description = "(required)"
  type        = string
}

variable "vm_image" {
  description = "(required)"
  type        = string
}

variable "azure_active_directory" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_application_id  = string
      cluster_application_id = string
      tenant_id              = string
    }
  ))
  default = []
}

variable "certificate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      thumbprint           = string
      thumbprint_secondary = string
      x509_store_name      = string
    }
  ))
  default = []
}

variable "certificate_common_names" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      common_names = set(object(
        {
          certificate_common_name       = string
          certificate_issuer_thumbprint = string
        }
      ))
      x509_store_name = string
    }
  ))
  default = []
}

variable "client_certificate_common_name" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      common_name       = string
      is_admin          = bool
      issuer_thumbprint = string
    }
  ))
  default = []
}

variable "client_certificate_thumbprint" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_admin   = bool
      thumbprint = string
    }
  ))
  default = []
}

variable "diagnostics_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      blob_endpoint              = string
      protected_account_key_name = string
      queue_endpoint             = string
      storage_account_name       = string
      table_endpoint             = string
    }
  ))
  default = []
}

variable "fabric_settings" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name       = string
      parameters = map(string)
    }
  ))
  default = []
}

variable "node_type" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      application_ports = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
      capacities           = map(string)
      client_endpoint_port = number
      durability_level     = string
      ephemeral_ports = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
      http_endpoint_port          = number
      instance_count              = number
      is_primary                  = bool
      name                        = string
      placement_properties        = map(string)
      reverse_proxy_endpoint_port = number
    }
  ))
}

variable "reverse_proxy_certificate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      thumbprint           = string
      thumbprint_secondary = string
      x509_store_name      = string
    }
  ))
  default = []
}

variable "reverse_proxy_certificate_common_names" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      common_names = set(object(
        {
          certificate_common_name       = string
          certificate_issuer_thumbprint = string
        }
      ))
      x509_store_name = string
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

variable "upgrade_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delta_health_policy = list(object(
        {
          max_delta_unhealthy_applications_percent         = number
          max_delta_unhealthy_nodes_percent                = number
          max_upgrade_domain_delta_unhealthy_nodes_percent = number
        }
      ))
      force_restart_enabled        = bool
      health_check_retry_timeout   = string
      health_check_stable_duration = string
      health_check_wait_duration   = string
      health_policy = list(object(
        {
          max_unhealthy_applications_percent = number
          max_unhealthy_nodes_percent        = number
        }
      ))
      upgrade_domain_timeout            = string
      upgrade_replica_set_check_timeout = string
      upgrade_timeout                   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_service_fabric_cluster" "this" {
  add_on_features      = var.add_on_features
  cluster_code_version = var.cluster_code_version
  location             = var.location
  management_endpoint  = var.management_endpoint
  name                 = var.name
  reliability_level    = var.reliability_level
  resource_group_name  = var.resource_group_name
  tags                 = var.tags
  upgrade_mode         = var.upgrade_mode
  vm_image             = var.vm_image

  dynamic "azure_active_directory" {
    for_each = var.azure_active_directory
    content {
      client_application_id  = azure_active_directory.value["client_application_id"]
      cluster_application_id = azure_active_directory.value["cluster_application_id"]
      tenant_id              = azure_active_directory.value["tenant_id"]
    }
  }

  dynamic "certificate" {
    for_each = var.certificate
    content {
      thumbprint           = certificate.value["thumbprint"]
      thumbprint_secondary = certificate.value["thumbprint_secondary"]
      x509_store_name      = certificate.value["x509_store_name"]
    }
  }

  dynamic "certificate_common_names" {
    for_each = var.certificate_common_names
    content {
      x509_store_name = certificate_common_names.value["x509_store_name"]

      dynamic "common_names" {
        for_each = certificate_common_names.value.common_names
        content {
          certificate_common_name       = common_names.value["certificate_common_name"]
          certificate_issuer_thumbprint = common_names.value["certificate_issuer_thumbprint"]
        }
      }

    }
  }

  dynamic "client_certificate_common_name" {
    for_each = var.client_certificate_common_name
    content {
      common_name       = client_certificate_common_name.value["common_name"]
      is_admin          = client_certificate_common_name.value["is_admin"]
      issuer_thumbprint = client_certificate_common_name.value["issuer_thumbprint"]
    }
  }

  dynamic "client_certificate_thumbprint" {
    for_each = var.client_certificate_thumbprint
    content {
      is_admin   = client_certificate_thumbprint.value["is_admin"]
      thumbprint = client_certificate_thumbprint.value["thumbprint"]
    }
  }

  dynamic "diagnostics_config" {
    for_each = var.diagnostics_config
    content {
      blob_endpoint              = diagnostics_config.value["blob_endpoint"]
      protected_account_key_name = diagnostics_config.value["protected_account_key_name"]
      queue_endpoint             = diagnostics_config.value["queue_endpoint"]
      storage_account_name       = diagnostics_config.value["storage_account_name"]
      table_endpoint             = diagnostics_config.value["table_endpoint"]
    }
  }

  dynamic "fabric_settings" {
    for_each = var.fabric_settings
    content {
      name       = fabric_settings.value["name"]
      parameters = fabric_settings.value["parameters"]
    }
  }

  dynamic "node_type" {
    for_each = var.node_type
    content {
      capacities                  = node_type.value["capacities"]
      client_endpoint_port        = node_type.value["client_endpoint_port"]
      durability_level            = node_type.value["durability_level"]
      http_endpoint_port          = node_type.value["http_endpoint_port"]
      instance_count              = node_type.value["instance_count"]
      is_primary                  = node_type.value["is_primary"]
      name                        = node_type.value["name"]
      placement_properties        = node_type.value["placement_properties"]
      reverse_proxy_endpoint_port = node_type.value["reverse_proxy_endpoint_port"]

      dynamic "application_ports" {
        for_each = node_type.value.application_ports
        content {
          end_port   = application_ports.value["end_port"]
          start_port = application_ports.value["start_port"]
        }
      }

      dynamic "ephemeral_ports" {
        for_each = node_type.value.ephemeral_ports
        content {
          end_port   = ephemeral_ports.value["end_port"]
          start_port = ephemeral_ports.value["start_port"]
        }
      }

    }
  }

  dynamic "reverse_proxy_certificate" {
    for_each = var.reverse_proxy_certificate
    content {
      thumbprint           = reverse_proxy_certificate.value["thumbprint"]
      thumbprint_secondary = reverse_proxy_certificate.value["thumbprint_secondary"]
      x509_store_name      = reverse_proxy_certificate.value["x509_store_name"]
    }
  }

  dynamic "reverse_proxy_certificate_common_names" {
    for_each = var.reverse_proxy_certificate_common_names
    content {
      x509_store_name = reverse_proxy_certificate_common_names.value["x509_store_name"]

      dynamic "common_names" {
        for_each = reverse_proxy_certificate_common_names.value.common_names
        content {
          certificate_common_name       = common_names.value["certificate_common_name"]
          certificate_issuer_thumbprint = common_names.value["certificate_issuer_thumbprint"]
        }
      }

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

  dynamic "upgrade_policy" {
    for_each = var.upgrade_policy
    content {
      force_restart_enabled             = upgrade_policy.value["force_restart_enabled"]
      health_check_retry_timeout        = upgrade_policy.value["health_check_retry_timeout"]
      health_check_stable_duration      = upgrade_policy.value["health_check_stable_duration"]
      health_check_wait_duration        = upgrade_policy.value["health_check_wait_duration"]
      upgrade_domain_timeout            = upgrade_policy.value["upgrade_domain_timeout"]
      upgrade_replica_set_check_timeout = upgrade_policy.value["upgrade_replica_set_check_timeout"]
      upgrade_timeout                   = upgrade_policy.value["upgrade_timeout"]

      dynamic "delta_health_policy" {
        for_each = upgrade_policy.value.delta_health_policy
        content {
          max_delta_unhealthy_applications_percent         = delta_health_policy.value["max_delta_unhealthy_applications_percent"]
          max_delta_unhealthy_nodes_percent                = delta_health_policy.value["max_delta_unhealthy_nodes_percent"]
          max_upgrade_domain_delta_unhealthy_nodes_percent = delta_health_policy.value["max_upgrade_domain_delta_unhealthy_nodes_percent"]
        }
      }

      dynamic "health_policy" {
        for_each = upgrade_policy.value.health_policy
        content {
          max_unhealthy_applications_percent = health_policy.value["max_unhealthy_applications_percent"]
          max_unhealthy_nodes_percent        = health_policy.value["max_unhealthy_nodes_percent"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_code_version" {
  description = "returns a string"
  value       = azurerm_service_fabric_cluster.this.cluster_code_version
}

output "cluster_endpoint" {
  description = "returns a string"
  value       = azurerm_service_fabric_cluster.this.cluster_endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_service_fabric_cluster.this.id
}

output "this" {
  value = azurerm_service_fabric_cluster.this
}
```

[top](#index)