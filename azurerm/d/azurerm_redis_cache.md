# azurerm_redis_cache

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
module "azurerm_redis_cache" {
  source = "./modules/azurerm/d/azurerm_redis_cache"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # zones - (optional) is a type of list of string
  zones = []

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

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
data "azurerm_redis_cache" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  zones               = var.zones

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
output "capacity" {
  description = "returns a number"
  value       = data.azurerm_redis_cache.this.capacity
}

output "enable_non_ssl_port" {
  description = "returns a bool"
  value       = data.azurerm_redis_cache.this.enable_non_ssl_port
}

output "family" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.family
}

output "hostname" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.location
}

output "minimum_tls_version" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.minimum_tls_version
}

output "patch_schedule" {
  description = "returns a list of object"
  value       = data.azurerm_redis_cache.this.patch_schedule
}

output "port" {
  description = "returns a number"
  value       = data.azurerm_redis_cache.this.port
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.primary_access_key
  sensitive   = true
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.primary_connection_string
  sensitive   = true
}

output "private_static_ip_address" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.private_static_ip_address
}

output "redis_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_redis_cache.this.redis_configuration
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.secondary_access_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.secondary_connection_string
  sensitive   = true
}

output "shard_count" {
  description = "returns a number"
  value       = data.azurerm_redis_cache.this.shard_count
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.sku_name
}

output "ssl_port" {
  description = "returns a number"
  value       = data.azurerm_redis_cache.this.ssl_port
}

output "subnet_id" {
  description = "returns a string"
  value       = data.azurerm_redis_cache.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_redis_cache.this.tags
}

output "zones" {
  description = "returns a list of string"
  value       = data.azurerm_redis_cache.this.zones
}

output "this" {
  value = azurerm_redis_cache.this
}
```

[top](#index)