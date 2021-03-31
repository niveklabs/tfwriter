# azurerm_kusto_database

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
module "azurerm_kusto_database" {
  source = "./modules/azurerm/r/azurerm_kusto_database"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # hot_cache_period - (optional) is a type of string
  hot_cache_period = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # soft_delete_period - (optional) is a type of string
  soft_delete_period = null

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
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "hot_cache_period" {
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "soft_delete_period" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_kusto_database" "this" {
  cluster_name        = var.cluster_name
  hot_cache_period    = var.hot_cache_period
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  soft_delete_period  = var.soft_delete_period

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
  value       = azurerm_kusto_database.this.id
}

output "size" {
  description = "returns a number"
  value       = azurerm_kusto_database.this.size
}

output "this" {
  value = azurerm_kusto_database.this
}
```

[top](#index)