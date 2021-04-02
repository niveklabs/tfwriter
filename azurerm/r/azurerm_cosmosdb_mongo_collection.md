# azurerm_cosmosdb_mongo_collection

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
module "azurerm_cosmosdb_mongo_collection" {
  source = "./modules/azurerm/r/azurerm_cosmosdb_mongo_collection"

  # account_name - (required) is a type of string
  account_name = null
  # database_name - (required) is a type of string
  database_name = null
  # default_ttl_seconds - (optional) is a type of number
  default_ttl_seconds = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # shard_key - (optional) is a type of string
  shard_key = null
  # throughput - (optional) is a type of number
  throughput = null

  autoscale_settings = [{
    max_throughput = null
  }]

  index = [{
    keys   = []
    unique = null
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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "default_ttl_seconds" {
  description = "(optional)"
  type        = number
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

variable "shard_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "throughput" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "autoscale_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_throughput = number
    }
  ))
  default = []
}

variable "index" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      keys   = list(string)
      unique = bool
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
resource "azurerm_cosmosdb_mongo_collection" "this" {
  account_name        = var.account_name
  database_name       = var.database_name
  default_ttl_seconds = var.default_ttl_seconds
  name                = var.name
  resource_group_name = var.resource_group_name
  shard_key           = var.shard_key
  throughput          = var.throughput

  dynamic "autoscale_settings" {
    for_each = var.autoscale_settings
    content {
      max_throughput = autoscale_settings.value["max_throughput"]
    }
  }

  dynamic "index" {
    for_each = var.index
    content {
      keys   = index.value["keys"]
      unique = index.value["unique"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_cosmosdb_mongo_collection.this.id
}

output "system_indexes" {
  description = "returns a list of object"
  value       = azurerm_cosmosdb_mongo_collection.this.system_indexes
}

output "throughput" {
  description = "returns a number"
  value       = azurerm_cosmosdb_mongo_collection.this.throughput
}

output "this" {
  value = azurerm_cosmosdb_mongo_collection.this
}
```

[top](#index)