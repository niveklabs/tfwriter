# azurerm_redis_cache

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
module "azurerm_redis_cache" {
  source = "./modules/azurerm/r/azurerm_redis_cache"

  # capacity - (required) is a type of number
  capacity = null
  # enable_non_ssl_port - (optional) is a type of bool
  enable_non_ssl_port = null
  # family - (required) is a type of string
  family = null
  # location - (required) is a type of string
  location = null
  # minimum_tls_version - (optional) is a type of string
  minimum_tls_version = null
  # name - (required) is a type of string
  name = null
  # private_static_ip_address - (optional) is a type of string
  private_static_ip_address = null
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # shard_count - (optional) is a type of number
  shard_count = null
  # sku_name - (required) is a type of string
  sku_name = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

  patch_schedule = [{
    day_of_week    = null
    start_hour_utc = null
  }]

  redis_configuration = [{
    aof_backup_enabled              = null
    aof_storage_connection_string_0 = null
    aof_storage_connection_string_1 = null
    enable_authentication           = null
    maxclients                      = null
    maxfragmentationmemory_reserved = null
    maxmemory_delta                 = null
    maxmemory_policy                = null
    maxmemory_reserved              = null
    notify_keyspace_events          = null
    rdb_backup_enabled              = null
    rdb_backup_frequency            = null
    rdb_backup_max_snapshot_count   = null
    rdb_storage_connection_string   = null
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
variable "capacity" {
  description = "(required)"
  type        = number
}

variable "enable_non_ssl_port" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "family" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "minimum_tls_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "private_static_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "shard_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "patch_schedule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      day_of_week    = string
      start_hour_utc = number
    }
  ))
  default = []
}

variable "redis_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aof_backup_enabled              = bool
      aof_storage_connection_string_0 = string
      aof_storage_connection_string_1 = string
      enable_authentication           = bool
      maxclients                      = number
      maxfragmentationmemory_reserved = number
      maxmemory_delta                 = number
      maxmemory_policy                = string
      maxmemory_reserved              = number
      notify_keyspace_events          = string
      rdb_backup_enabled              = bool
      rdb_backup_frequency            = number
      rdb_backup_max_snapshot_count   = number
      rdb_storage_connection_string   = string
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
resource "azurerm_redis_cache" "this" {
  capacity                      = var.capacity
  enable_non_ssl_port           = var.enable_non_ssl_port
  family                        = var.family
  location                      = var.location
  minimum_tls_version           = var.minimum_tls_version
  name                          = var.name
  private_static_ip_address     = var.private_static_ip_address
  public_network_access_enabled = var.public_network_access_enabled
  resource_group_name           = var.resource_group_name
  shard_count                   = var.shard_count
  sku_name                      = var.sku_name
  subnet_id                     = var.subnet_id
  tags                          = var.tags
  zones                         = var.zones

  dynamic "patch_schedule" {
    for_each = var.patch_schedule
    content {
      day_of_week    = patch_schedule.value["day_of_week"]
      start_hour_utc = patch_schedule.value["start_hour_utc"]
    }
  }

  dynamic "redis_configuration" {
    for_each = var.redis_configuration
    content {
      aof_backup_enabled              = redis_configuration.value["aof_backup_enabled"]
      aof_storage_connection_string_0 = redis_configuration.value["aof_storage_connection_string_0"]
      aof_storage_connection_string_1 = redis_configuration.value["aof_storage_connection_string_1"]
      enable_authentication           = redis_configuration.value["enable_authentication"]
      maxfragmentationmemory_reserved = redis_configuration.value["maxfragmentationmemory_reserved"]
      maxmemory_delta                 = redis_configuration.value["maxmemory_delta"]
      maxmemory_policy                = redis_configuration.value["maxmemory_policy"]
      maxmemory_reserved              = redis_configuration.value["maxmemory_reserved"]
      notify_keyspace_events          = redis_configuration.value["notify_keyspace_events"]
      rdb_backup_enabled              = redis_configuration.value["rdb_backup_enabled"]
      rdb_backup_frequency            = redis_configuration.value["rdb_backup_frequency"]
      rdb_backup_max_snapshot_count   = redis_configuration.value["rdb_backup_max_snapshot_count"]
      rdb_storage_connection_string   = redis_configuration.value["rdb_storage_connection_string"]
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
output "hostname" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.hostname
}

output "id" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.id
}

output "port" {
  description = "returns a number"
  value       = azurerm_redis_cache.this.port
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.primary_access_key
  sensitive   = true
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.primary_connection_string
  sensitive   = true
}

output "private_static_ip_address" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.private_static_ip_address
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.secondary_access_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_redis_cache.this.secondary_connection_string
  sensitive   = true
}

output "ssl_port" {
  description = "returns a number"
  value       = azurerm_redis_cache.this.ssl_port
}

output "this" {
  value = azurerm_redis_cache.this
}
```

[top](#index)