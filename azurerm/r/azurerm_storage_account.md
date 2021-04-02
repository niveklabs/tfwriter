# azurerm_storage_account

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
module "azurerm_storage_account" {
  source = "./modules/azurerm/r/azurerm_storage_account"

  # access_tier - (optional) is a type of string
  access_tier = null
  # account_kind - (optional) is a type of string
  account_kind = null
  # account_replication_type - (required) is a type of string
  account_replication_type = null
  # account_tier - (required) is a type of string
  account_tier = null
  # allow_blob_public_access - (optional) is a type of bool
  allow_blob_public_access = null
  # enable_https_traffic_only - (optional) is a type of bool
  enable_https_traffic_only = null
  # is_hns_enabled - (optional) is a type of bool
  is_hns_enabled = null
  # large_file_share_enabled - (optional) is a type of bool
  large_file_share_enabled = null
  # location - (required) is a type of string
  location = null
  # min_tls_version - (optional) is a type of string
  min_tls_version = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  blob_properties = [{
    container_delete_retention_policy = [{
      days = null
    }]
    cors_rule = [{
      allowed_headers    = []
      allowed_methods    = []
      allowed_origins    = []
      exposed_headers    = []
      max_age_in_seconds = null
    }]
    delete_retention_policy = [{
      days = null
    }]
  }]

  custom_domain = [{
    name          = null
    use_subdomain = null
  }]

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  network_rules = [{
    bypass                     = []
    default_action             = null
    ip_rules                   = []
    virtual_network_subnet_ids = []
  }]

  queue_properties = [{
    cors_rule = [{
      allowed_headers    = []
      allowed_methods    = []
      allowed_origins    = []
      exposed_headers    = []
      max_age_in_seconds = null
    }]
    hour_metrics = [{
      enabled               = null
      include_apis          = null
      retention_policy_days = null
      version               = null
    }]
    logging = [{
      delete                = null
      read                  = null
      retention_policy_days = null
      version               = null
      write                 = null
    }]
    minute_metrics = [{
      enabled               = null
      include_apis          = null
      retention_policy_days = null
      version               = null
    }]
  }]

  static_website = [{
    error_404_document = null
    index_document     = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_kind" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_replication_type" {
  description = "(required)"
  type        = string
}

variable "account_tier" {
  description = "(required)"
  type        = string
}

variable "allow_blob_public_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_https_traffic_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_hns_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "large_file_share_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "min_tls_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
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

variable "blob_properties" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      container_delete_retention_policy = list(object(
        {
          days = number
        }
      ))
      cors_rule = list(object(
        {
          allowed_headers    = list(string)
          allowed_methods    = list(string)
          allowed_origins    = list(string)
          exposed_headers    = list(string)
          max_age_in_seconds = number
        }
      ))
      delete_retention_policy = list(object(
        {
          days = number
        }
      ))
    }
  ))
  default = []
}

variable "custom_domain" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name          = string
      use_subdomain = bool
    }
  ))
  default = []
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "network_rules" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bypass                     = set(string)
      default_action             = string
      ip_rules                   = set(string)
      virtual_network_subnet_ids = set(string)
    }
  ))
  default = []
}

variable "queue_properties" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cors_rule = list(object(
        {
          allowed_headers    = list(string)
          allowed_methods    = list(string)
          allowed_origins    = list(string)
          exposed_headers    = list(string)
          max_age_in_seconds = number
        }
      ))
      hour_metrics = list(object(
        {
          enabled               = bool
          include_apis          = bool
          retention_policy_days = number
          version               = string
        }
      ))
      logging = list(object(
        {
          delete                = bool
          read                  = bool
          retention_policy_days = number
          version               = string
          write                 = bool
        }
      ))
      minute_metrics = list(object(
        {
          enabled               = bool
          include_apis          = bool
          retention_policy_days = number
          version               = string
        }
      ))
    }
  ))
  default = []
}

variable "static_website" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      error_404_document = string
      index_document     = string
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
```

[top](#index)

### Resource

```terraform
resource "azurerm_storage_account" "this" {
  access_tier               = var.access_tier
  account_kind              = var.account_kind
  account_replication_type  = var.account_replication_type
  account_tier              = var.account_tier
  allow_blob_public_access  = var.allow_blob_public_access
  enable_https_traffic_only = var.enable_https_traffic_only
  is_hns_enabled            = var.is_hns_enabled
  large_file_share_enabled  = var.large_file_share_enabled
  location                  = var.location
  min_tls_version           = var.min_tls_version
  name                      = var.name
  resource_group_name       = var.resource_group_name
  tags                      = var.tags

  dynamic "blob_properties" {
    for_each = var.blob_properties
    content {

      dynamic "container_delete_retention_policy" {
        for_each = blob_properties.value.container_delete_retention_policy
        content {
          days = container_delete_retention_policy.value["days"]
        }
      }

      dynamic "cors_rule" {
        for_each = blob_properties.value.cors_rule
        content {
          allowed_headers    = cors_rule.value["allowed_headers"]
          allowed_methods    = cors_rule.value["allowed_methods"]
          allowed_origins    = cors_rule.value["allowed_origins"]
          exposed_headers    = cors_rule.value["exposed_headers"]
          max_age_in_seconds = cors_rule.value["max_age_in_seconds"]
        }
      }

      dynamic "delete_retention_policy" {
        for_each = blob_properties.value.delete_retention_policy
        content {
          days = delete_retention_policy.value["days"]
        }
      }

    }
  }

  dynamic "custom_domain" {
    for_each = var.custom_domain
    content {
      name          = custom_domain.value["name"]
      use_subdomain = custom_domain.value["use_subdomain"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
    }
  }

  dynamic "network_rules" {
    for_each = var.network_rules
    content {
      bypass                     = network_rules.value["bypass"]
      default_action             = network_rules.value["default_action"]
      ip_rules                   = network_rules.value["ip_rules"]
      virtual_network_subnet_ids = network_rules.value["virtual_network_subnet_ids"]
    }
  }

  dynamic "queue_properties" {
    for_each = var.queue_properties
    content {

      dynamic "cors_rule" {
        for_each = queue_properties.value.cors_rule
        content {
          allowed_headers    = cors_rule.value["allowed_headers"]
          allowed_methods    = cors_rule.value["allowed_methods"]
          allowed_origins    = cors_rule.value["allowed_origins"]
          exposed_headers    = cors_rule.value["exposed_headers"]
          max_age_in_seconds = cors_rule.value["max_age_in_seconds"]
        }
      }

      dynamic "hour_metrics" {
        for_each = queue_properties.value.hour_metrics
        content {
          enabled               = hour_metrics.value["enabled"]
          include_apis          = hour_metrics.value["include_apis"]
          retention_policy_days = hour_metrics.value["retention_policy_days"]
          version               = hour_metrics.value["version"]
        }
      }

      dynamic "logging" {
        for_each = queue_properties.value.logging
        content {
          delete                = logging.value["delete"]
          read                  = logging.value["read"]
          retention_policy_days = logging.value["retention_policy_days"]
          version               = logging.value["version"]
          write                 = logging.value["write"]
        }
      }

      dynamic "minute_metrics" {
        for_each = queue_properties.value.minute_metrics
        content {
          enabled               = minute_metrics.value["enabled"]
          include_apis          = minute_metrics.value["include_apis"]
          retention_policy_days = minute_metrics.value["retention_policy_days"]
          version               = minute_metrics.value["version"]
        }
      }

    }
  }

  dynamic "static_website" {
    for_each = var.static_website
    content {
      error_404_document = static_website.value["error_404_document"]
      index_document     = static_website.value["index_document"]
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

}
```

[top](#index)

### Outputs

```terraform
output "access_tier" {
  description = "returns a string"
  value       = azurerm_storage_account.this.access_tier
}

output "id" {
  description = "returns a string"
  value       = azurerm_storage_account.this.id
}

output "large_file_share_enabled" {
  description = "returns a bool"
  value       = azurerm_storage_account.this.large_file_share_enabled
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_access_key
  sensitive   = true
}

output "primary_blob_connection_string" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_blob_connection_string
  sensitive   = true
}

output "primary_blob_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_blob_endpoint
}

output "primary_blob_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_blob_host
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_connection_string
  sensitive   = true
}

output "primary_dfs_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_dfs_endpoint
}

output "primary_dfs_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_dfs_host
}

output "primary_file_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_file_endpoint
}

output "primary_file_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_file_host
}

output "primary_location" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_location
}

output "primary_queue_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_queue_endpoint
}

output "primary_queue_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_queue_host
}

output "primary_table_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_table_endpoint
}

output "primary_table_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_table_host
}

output "primary_web_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_web_endpoint
}

output "primary_web_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.primary_web_host
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_access_key
  sensitive   = true
}

output "secondary_blob_connection_string" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_blob_connection_string
  sensitive   = true
}

output "secondary_blob_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_blob_endpoint
}

output "secondary_blob_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_blob_host
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_connection_string
  sensitive   = true
}

output "secondary_dfs_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_dfs_endpoint
}

output "secondary_dfs_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_dfs_host
}

output "secondary_file_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_file_endpoint
}

output "secondary_file_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_file_host
}

output "secondary_location" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_location
}

output "secondary_queue_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_queue_endpoint
}

output "secondary_queue_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_queue_host
}

output "secondary_table_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_table_endpoint
}

output "secondary_table_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_table_host
}

output "secondary_web_endpoint" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_web_endpoint
}

output "secondary_web_host" {
  description = "returns a string"
  value       = azurerm_storage_account.this.secondary_web_host
}

output "this" {
  value = azurerm_storage_account.this
}
```

[top](#index)