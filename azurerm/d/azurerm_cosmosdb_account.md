# azurerm_cosmosdb_account

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
module "azurerm_cosmosdb_account" {
  source = "./modules/azurerm/d/azurerm_cosmosdb_account"

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
data "azurerm_cosmosdb_account" "this" {
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
output "capabilities" {
  description = "returns a list of object"
  value       = data.azurerm_cosmosdb_account.this.capabilities
}

output "consistency_policy" {
  description = "returns a list of object"
  value       = data.azurerm_cosmosdb_account.this.consistency_policy
}

output "enable_automatic_failover" {
  description = "returns a bool"
  value       = data.azurerm_cosmosdb_account.this.enable_automatic_failover
}

output "enable_free_tier" {
  description = "returns a bool"
  value       = data.azurerm_cosmosdb_account.this.enable_free_tier
}

output "enable_multiple_write_locations" {
  description = "returns a bool"
  value       = data.azurerm_cosmosdb_account.this.enable_multiple_write_locations
}

output "endpoint" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.endpoint
}

output "geo_location" {
  description = "returns a list of object"
  value       = data.azurerm_cosmosdb_account.this.geo_location
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.id
}

output "ip_range_filter" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.ip_range_filter
}

output "is_virtual_network_filter_enabled" {
  description = "returns a bool"
  value       = data.azurerm_cosmosdb_account.this.is_virtual_network_filter_enabled
}

output "key_vault_key_id" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.key_vault_key_id
}

output "kind" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.kind
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.location
}

output "offer_type" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.offer_type
}

output "primary_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.primary_key
  sensitive   = true
}

output "primary_master_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.primary_master_key
  sensitive   = true
}

output "primary_readonly_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.primary_readonly_key
  sensitive   = true
}

output "primary_readonly_master_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.primary_readonly_master_key
  sensitive   = true
}

output "read_endpoints" {
  description = "returns a list of string"
  value       = data.azurerm_cosmosdb_account.this.read_endpoints
}

output "secondary_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.secondary_key
  sensitive   = true
}

output "secondary_master_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.secondary_master_key
  sensitive   = true
}

output "secondary_readonly_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.secondary_readonly_key
  sensitive   = true
}

output "secondary_readonly_master_key" {
  description = "returns a string"
  value       = data.azurerm_cosmosdb_account.this.secondary_readonly_master_key
  sensitive   = true
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_cosmosdb_account.this.tags
}

output "virtual_network_rule" {
  description = "returns a list of object"
  value       = data.azurerm_cosmosdb_account.this.virtual_network_rule
}

output "write_endpoints" {
  description = "returns a list of string"
  value       = data.azurerm_cosmosdb_account.this.write_endpoints
}

output "this" {
  value = azurerm_cosmosdb_account.this
}
```

[top](#index)