# azurerm_eventhub_namespace

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_eventhub_namespace" {
  source = "./modules/azurerm/d/azurerm_eventhub_namespace"

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
data "azurerm_eventhub_namespace" "this" {
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
output "auto_inflate_enabled" {
  description = "returns a bool"
  value       = data.azurerm_eventhub_namespace.this.auto_inflate_enabled
}

output "capacity" {
  description = "returns a number"
  value       = data.azurerm_eventhub_namespace.this.capacity
}

output "dedicated_cluster_id" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.dedicated_cluster_id
}

output "default_primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.default_primary_connection_string
  sensitive   = true
}

output "default_primary_connection_string_alias" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.default_primary_connection_string_alias
  sensitive   = true
}

output "default_primary_key" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.default_primary_key
  sensitive   = true
}

output "default_secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.default_secondary_connection_string
  sensitive   = true
}

output "default_secondary_connection_string_alias" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.default_secondary_connection_string_alias
  sensitive   = true
}

output "default_secondary_key" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.default_secondary_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.id
}

output "kafka_enabled" {
  description = "returns a bool"
  value       = data.azurerm_eventhub_namespace.this.kafka_enabled
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.location
}

output "maximum_throughput_units" {
  description = "returns a number"
  value       = data.azurerm_eventhub_namespace.this.maximum_throughput_units
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_eventhub_namespace.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_eventhub_namespace.this.tags
}

output "zone_redundant" {
  description = "returns a bool"
  value       = data.azurerm_eventhub_namespace.this.zone_redundant
}

output "this" {
  value = azurerm_eventhub_namespace.this
}
```

[top](#index)