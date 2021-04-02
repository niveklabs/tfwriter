# azurerm_cosmosdb_cassandra_table

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
module "azurerm_cosmosdb_cassandra_table" {
  source = "./modules/azurerm/r/azurerm_cosmosdb_cassandra_table"

  # cassandra_keyspace_id - (required) is a type of string
  cassandra_keyspace_id = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # name - (required) is a type of string
  name = null
  # throughput - (optional) is a type of number
  throughput = null

  autoscale_settings = [{
    max_throughput = null
  }]

  schema = [{
    cluster_key = [{
      name     = null
      order_by = null
    }]
    column = [{
      name = null
      type = null
    }]
    partition_key = [{
      name = null
    }]
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
variable "cassandra_keyspace_id" {
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

variable "schema" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cluster_key = list(object(
        {
          name     = string
          order_by = string
        }
      ))
      column = list(object(
        {
          name = string
          type = string
        }
      ))
      partition_key = list(object(
        {
          name = string
        }
      ))
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
```

[top](#index)

### Resource

```terraform
resource "azurerm_cosmosdb_cassandra_table" "this" {
  cassandra_keyspace_id = var.cassandra_keyspace_id
  default_ttl           = var.default_ttl
  name                  = var.name
  throughput            = var.throughput

  dynamic "autoscale_settings" {
    for_each = var.autoscale_settings
    content {
      max_throughput = autoscale_settings.value["max_throughput"]
    }
  }

  dynamic "schema" {
    for_each = var.schema
    content {

      dynamic "cluster_key" {
        for_each = schema.value.cluster_key
        content {
          name     = cluster_key.value["name"]
          order_by = cluster_key.value["order_by"]
        }
      }

      dynamic "column" {
        for_each = schema.value.column
        content {
          name = column.value["name"]
          type = column.value["type"]
        }
      }

      dynamic "partition_key" {
        for_each = schema.value.partition_key
        content {
          name = partition_key.value["name"]
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

}
```

[top](#index)

### Outputs

```terraform
output "default_ttl" {
  description = "returns a number"
  value       = azurerm_cosmosdb_cassandra_table.this.default_ttl
}

output "id" {
  description = "returns a string"
  value       = azurerm_cosmosdb_cassandra_table.this.id
}

output "throughput" {
  description = "returns a number"
  value       = azurerm_cosmosdb_cassandra_table.this.throughput
}

output "this" {
  value = azurerm_cosmosdb_cassandra_table.this
}
```

[top](#index)