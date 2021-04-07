# azurerm_search_service

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_search_service" {
  source = "./modules/azurerm/d/azurerm_search_service"

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
data "azurerm_search_service" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_search_service.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_search_service.this.identity
}

output "partition_count" {
  description = "returns a number"
  value       = data.azurerm_search_service.this.partition_count
}

output "primary_key" {
  description = "returns a string"
  value       = data.azurerm_search_service.this.primary_key
  sensitive   = true
}

output "public_network_access_enabled" {
  description = "returns a bool"
  value       = data.azurerm_search_service.this.public_network_access_enabled
}

output "query_keys" {
  description = "returns a list of object"
  value       = data.azurerm_search_service.this.query_keys
}

output "replica_count" {
  description = "returns a number"
  value       = data.azurerm_search_service.this.replica_count
}

output "secondary_key" {
  description = "returns a string"
  value       = data.azurerm_search_service.this.secondary_key
  sensitive   = true
}

output "this" {
  value = azurerm_search_service.this
}
```

[top](#index)