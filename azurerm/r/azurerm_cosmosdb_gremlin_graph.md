# azurerm_cosmosdb_gremlin_graph

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_cosmosdb_gremlin_graph" {
  source = "./modules/azurerm/r/azurerm_cosmosdb_gremlin_graph"

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
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # throughput - (optional) is a type of number
  throughput = null

  autoscale_settings = [{
    max_throughput = null
  }]

  conflict_resolution_policy = [{
    conflict_resolution_path      = null
    conflict_resolution_procedure = null
    mode                          = null
  }]

  index_policy = [{
    automatic      = null
    excluded_paths = []
    included_paths = []
    indexing_mode  = null
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

variable "conflict_resolution_policy" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      conflict_resolution_path      = string
      conflict_resolution_procedure = string
      mode                          = string
    }
  ))
}

variable "index_policy" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      automatic      = bool
      excluded_paths = set(string)
      included_paths = set(string)
      indexing_mode  = string
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
resource "azurerm_cosmosdb_gremlin_graph" "this" {
  account_name        = var.account_name
  database_name       = var.database_name
  default_ttl         = var.default_ttl
  name                = var.name
  partition_key_path  = var.partition_key_path
  resource_group_name = var.resource_group_name
  throughput          = var.throughput

  dynamic "autoscale_settings" {
    for_each = var.autoscale_settings
    content {
      max_throughput = autoscale_settings.value["max_throughput"]
    }
  }

  dynamic "conflict_resolution_policy" {
    for_each = var.conflict_resolution_policy
    content {
      conflict_resolution_path      = conflict_resolution_policy.value["conflict_resolution_path"]
      conflict_resolution_procedure = conflict_resolution_policy.value["conflict_resolution_procedure"]
      mode                          = conflict_resolution_policy.value["mode"]
    }
  }

  dynamic "index_policy" {
    for_each = var.index_policy
    content {
      automatic      = index_policy.value["automatic"]
      excluded_paths = index_policy.value["excluded_paths"]
      included_paths = index_policy.value["included_paths"]
      indexing_mode  = index_policy.value["indexing_mode"]
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
  value       = azurerm_cosmosdb_gremlin_graph.this.default_ttl
}

output "id" {
  description = "returns a string"
  value       = azurerm_cosmosdb_gremlin_graph.this.id
}

output "throughput" {
  description = "returns a number"
  value       = azurerm_cosmosdb_gremlin_graph.this.throughput
}

output "this" {
  value = azurerm_cosmosdb_gremlin_graph.this
}
```

[top](#index)