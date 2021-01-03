# azurerm_cosmosdb_account

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_cosmosdb_account" {
  source = "./modules/azurerm/r/azurerm_cosmosdb_account"

  # enable_automatic_failover - (optional) is a type of bool
  enable_automatic_failover = null
  # enable_free_tier - (optional) is a type of bool
  enable_free_tier = null
  # enable_multiple_write_locations - (optional) is a type of bool
  enable_multiple_write_locations = null
  # ip_range_filter - (optional) is a type of string
  ip_range_filter = null
  # is_virtual_network_filter_enabled - (optional) is a type of bool
  is_virtual_network_filter_enabled = null
  # key_vault_key_id - (optional) is a type of string
  key_vault_key_id = null
  # kind - (optional) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # offer_type - (required) is a type of string
  offer_type = null
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  capabilities = [{
    name = null
  }]

  consistency_policy = [{
    consistency_level       = null
    max_interval_in_seconds = null
    max_staleness_prefix    = null
  }]

  geo_location = [{
    failover_priority = null
    id                = null
    location          = null
    prefix            = null
    zone_redundant    = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  virtual_network_rule = [{
    id                                   = null
    ignore_missing_vnet_service_endpoint = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_automatic_failover" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_free_tier" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_multiple_write_locations" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_range_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_virtual_network_filter_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_vault_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kind" {
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

variable "offer_type" {
  description = "(required)"
  type        = string
}

variable "public_network_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "capabilities" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "consistency_policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      consistency_level       = string
      max_interval_in_seconds = number
      max_staleness_prefix    = number
    }
  ))
}

variable "geo_location" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      failover_priority = number
      id                = string
      location          = string
      prefix            = string
      zone_redundant    = bool
    }
  ))
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

variable "virtual_network_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id                                   = string
      ignore_missing_vnet_service_endpoint = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_cosmosdb_account" "this" {
  enable_automatic_failover         = var.enable_automatic_failover
  enable_free_tier                  = var.enable_free_tier
  enable_multiple_write_locations   = var.enable_multiple_write_locations
  ip_range_filter                   = var.ip_range_filter
  is_virtual_network_filter_enabled = var.is_virtual_network_filter_enabled
  key_vault_key_id                  = var.key_vault_key_id
  kind                              = var.kind
  location                          = var.location
  name                              = var.name
  offer_type                        = var.offer_type
  public_network_access_enabled     = var.public_network_access_enabled
  resource_group_name               = var.resource_group_name
  tags                              = var.tags

  dynamic "capabilities" {
    for_each = var.capabilities
    content {
      name = capabilities.value["name"]
    }
  }

  dynamic "consistency_policy" {
    for_each = var.consistency_policy
    content {
      consistency_level       = consistency_policy.value["consistency_level"]
      max_interval_in_seconds = consistency_policy.value["max_interval_in_seconds"]
      max_staleness_prefix    = consistency_policy.value["max_staleness_prefix"]
    }
  }

  dynamic "geo_location" {
    for_each = var.geo_location
    content {
      failover_priority = geo_location.value["failover_priority"]
      location          = geo_location.value["location"]
      prefix            = geo_location.value["prefix"]
      zone_redundant    = geo_location.value["zone_redundant"]
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

  dynamic "virtual_network_rule" {
    for_each = var.virtual_network_rule
    content {
      id                                   = virtual_network_rule.value["id"]
      ignore_missing_vnet_service_endpoint = virtual_network_rule.value["ignore_missing_vnet_service_endpoint"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "connection_strings" {
  description = "returns a list of string"
  value       = azurerm_cosmosdb_account.this.connection_strings
  sensitive   = true
}

output "endpoint" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.id
}

output "primary_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.primary_key
  sensitive   = true
}

output "primary_master_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.primary_master_key
  sensitive   = true
}

output "primary_readonly_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.primary_readonly_key
  sensitive   = true
}

output "primary_readonly_master_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.primary_readonly_master_key
  sensitive   = true
}

output "read_endpoints" {
  description = "returns a list of string"
  value       = azurerm_cosmosdb_account.this.read_endpoints
}

output "secondary_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.secondary_key
  sensitive   = true
}

output "secondary_master_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.secondary_master_key
  sensitive   = true
}

output "secondary_readonly_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.secondary_readonly_key
  sensitive   = true
}

output "secondary_readonly_master_key" {
  description = "returns a string"
  value       = azurerm_cosmosdb_account.this.secondary_readonly_master_key
  sensitive   = true
}

output "write_endpoints" {
  description = "returns a list of string"
  value       = azurerm_cosmosdb_account.this.write_endpoints
}

output "this" {
  value = azurerm_cosmosdb_account.this
}
```

[top](#index)