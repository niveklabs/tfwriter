# azurerm_mssql_elasticpool

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
module "azurerm_mssql_elasticpool" {
  source = "./modules/azurerm/r/azurerm_mssql_elasticpool"

  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # max_size_bytes - (optional) is a type of number
  max_size_bytes = null
  # max_size_gb - (optional) is a type of number
  max_size_gb = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server_name - (required) is a type of string
  server_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_redundant - (optional) is a type of bool
  zone_redundant = null

  per_database_settings = [{
    max_capacity = null
    min_capacity = null
  }]

  sku = [{
    capacity = null
    family   = null
    name     = null
    tier     = null
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
variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "max_size_bytes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_size_gb" {
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

variable "server_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_redundant" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "per_database_settings" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      max_capacity = number
      min_capacity = number
    }
  ))
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      family   = string
      name     = string
      tier     = string
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
resource "azurerm_mssql_elasticpool" "this" {
  license_type        = var.license_type
  location            = var.location
  max_size_bytes      = var.max_size_bytes
  max_size_gb         = var.max_size_gb
  name                = var.name
  resource_group_name = var.resource_group_name
  server_name         = var.server_name
  tags                = var.tags
  zone_redundant      = var.zone_redundant

  dynamic "per_database_settings" {
    for_each = var.per_database_settings
    content {
      max_capacity = per_database_settings.value["max_capacity"]
      min_capacity = per_database_settings.value["min_capacity"]
    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      capacity = sku.value["capacity"]
      family   = sku.value["family"]
      name     = sku.value["name"]
      tier     = sku.value["tier"]
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
  value       = azurerm_mssql_elasticpool.this.id
}

output "license_type" {
  description = "returns a string"
  value       = azurerm_mssql_elasticpool.this.license_type
}

output "max_size_bytes" {
  description = "returns a number"
  value       = azurerm_mssql_elasticpool.this.max_size_bytes
}

output "max_size_gb" {
  description = "returns a number"
  value       = azurerm_mssql_elasticpool.this.max_size_gb
}

output "this" {
  value = azurerm_mssql_elasticpool.this
}
```

[top](#index)