# azurerm_cosmosdb_sql_container

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
module "azurerm_cosmosdb_sql_container" {
  source = "./modules/azurerm/r/azurerm_cosmosdb_sql_container"

  # account_name - (required) is a type of string
  account_name = null
  # database_name - (required) is a type of string
  database_name = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # name - (required) is a type of string
  name = null
  # partition_key_path - (optional) is a type of string
  partition_key_path = null
  # partition_key_version - (optional) is a type of number
  partition_key_version = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # throughput - (optional) is a type of number
  throughput = null

  autoscale_settings = [{
    max_throughput = null
  }]

  indexing_policy = [{
    composite_index = [{
      index = [{
        order = null
        path  = null
      }]
    }]
    excluded_path = [{
      path = null
    }]
    included_path = [{
      path = null
    }]
    indexing_mode = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  unique_key = [{
    paths = []
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

variable "default_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "partition_key_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "partition_key_version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
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

variable "indexing_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      composite_index = list(object(
        {
          index = list(object(
            {
              order = string
              path  = string
            }
          ))
        }
      ))
      excluded_path = list(object(
        {
          path = string
        }
      ))
      included_path = list(object(
        {
          path = string
        }
      ))
      indexing_mode = string
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

variable "unique_key" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      paths = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_cosmosdb_sql_container" "this" {
  account_name          = var.account_name
  database_name         = var.database_name
  default_ttl           = var.default_ttl
  name                  = var.name
  partition_key_path    = var.partition_key_path
  partition_key_version = var.partition_key_version
  resource_group_name   = var.resource_group_name
  throughput            = var.throughput

  dynamic "autoscale_settings" {
    for_each = var.autoscale_settings
    content {
      max_throughput = autoscale_settings.value["max_throughput"]
    }
  }

  dynamic "indexing_policy" {
    for_each = var.indexing_policy
    content {
      indexing_mode = indexing_policy.value["indexing_mode"]

      dynamic "composite_index" {
        for_each = indexing_policy.value.composite_index
        content {

          dynamic "index" {
            for_each = composite_index.value.index
            content {
              order = index.value["order"]
              path  = index.value["path"]
            }
          }

        }
      }

      dynamic "excluded_path" {
        for_each = indexing_policy.value.excluded_path
        content {
          path = excluded_path.value["path"]
        }
      }

      dynamic "included_path" {
        for_each = indexing_policy.value.included_path
        content {
          path = included_path.value["path"]
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

  dynamic "unique_key" {
    for_each = var.unique_key
    content {
      paths = unique_key.value["paths"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_ttl" {
  description = "returns a number"
  value       = azurerm_cosmosdb_sql_container.this.default_ttl
}

output "id" {
  description = "returns a string"
  value       = azurerm_cosmosdb_sql_container.this.id
}

output "throughput" {
  description = "returns a number"
  value       = azurerm_cosmosdb_sql_container.this.throughput
}

output "this" {
  value = azurerm_cosmosdb_sql_container.this
}
```

[top](#index)