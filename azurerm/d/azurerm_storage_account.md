# azurerm_storage_account

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
module "azurerm_storage_account" {
  source = "./modules/azurerm/d/azurerm_storage_account"

  # min_tls_version - (optional) is a type of string
  min_tls_version = null
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
data "azurerm_storage_account" "this" {
  min_tls_version     = var.min_tls_version
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
output "access_tier" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.access_tier
}

output "account_kind" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.account_kind
}

output "account_replication_type" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.account_replication_type
}

output "account_tier" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.account_tier
}

output "allow_blob_public_access" {
  description = "returns a bool"
  value       = data.azurerm_storage_account.this.allow_blob_public_access
}

output "custom_domain" {
  description = "returns a list of object"
  value       = data.azurerm_storage_account.this.custom_domain
}

output "enable_https_traffic_only" {
  description = "returns a bool"
  value       = data.azurerm_storage_account.this.enable_https_traffic_only
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.id
}

output "is_hns_enabled" {
  description = "returns a bool"
  value       = data.azurerm_storage_account.this.is_hns_enabled
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.location
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_access_key
  sensitive   = true
}

output "primary_blob_connection_string" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_blob_connection_string
  sensitive   = true
}

output "primary_blob_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_blob_endpoint
}

output "primary_blob_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_blob_host
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_connection_string
  sensitive   = true
}

output "primary_dfs_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_dfs_endpoint
}

output "primary_dfs_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_dfs_host
}

output "primary_file_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_file_endpoint
}

output "primary_file_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_file_host
}

output "primary_location" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_location
}

output "primary_queue_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_queue_endpoint
}

output "primary_queue_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_queue_host
}

output "primary_table_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_table_endpoint
}

output "primary_table_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_table_host
}

output "primary_web_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_web_endpoint
}

output "primary_web_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.primary_web_host
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_access_key
  sensitive   = true
}

output "secondary_blob_connection_string" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_blob_connection_string
  sensitive   = true
}

output "secondary_blob_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_blob_endpoint
}

output "secondary_blob_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_blob_host
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_connection_string
  sensitive   = true
}

output "secondary_dfs_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_dfs_endpoint
}

output "secondary_dfs_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_dfs_host
}

output "secondary_file_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_file_endpoint
}

output "secondary_file_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_file_host
}

output "secondary_location" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_location
}

output "secondary_queue_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_queue_endpoint
}

output "secondary_queue_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_queue_host
}

output "secondary_table_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_table_endpoint
}

output "secondary_table_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_table_host
}

output "secondary_web_endpoint" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_web_endpoint
}

output "secondary_web_host" {
  description = "returns a string"
  value       = data.azurerm_storage_account.this.secondary_web_host
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_storage_account.this.tags
}

output "this" {
  value = azurerm_storage_account.this
}
```

[top](#index)