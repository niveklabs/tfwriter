# azurerm_sql_elasticpool

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
module "azurerm_sql_elasticpool" {
  source = "./modules/azurerm/r/azurerm_sql_elasticpool"

  # db_dtu_max - (optional) is a type of number
  db_dtu_max = null
  # db_dtu_min - (optional) is a type of number
  db_dtu_min = null
  # dtu - (required) is a type of number
  dtu = null
  # edition - (required) is a type of string
  edition = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # pool_size - (optional) is a type of number
  pool_size = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server_name - (required) is a type of string
  server_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "db_dtu_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "db_dtu_min" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dtu" {
  description = "(required)"
  type        = number
}

variable "edition" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pool_size" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "azurerm_sql_elasticpool" "this" {
  db_dtu_max          = var.db_dtu_max
  db_dtu_min          = var.db_dtu_min
  dtu                 = var.dtu
  edition             = var.edition
  location            = var.location
  name                = var.name
  pool_size           = var.pool_size
  resource_group_name = var.resource_group_name
  server_name         = var.server_name
  tags                = var.tags

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
output "creation_date" {
  description = "returns a string"
  value       = azurerm_sql_elasticpool.this.creation_date
}

output "db_dtu_max" {
  description = "returns a number"
  value       = azurerm_sql_elasticpool.this.db_dtu_max
}

output "db_dtu_min" {
  description = "returns a number"
  value       = azurerm_sql_elasticpool.this.db_dtu_min
}

output "id" {
  description = "returns a string"
  value       = azurerm_sql_elasticpool.this.id
}

output "pool_size" {
  description = "returns a number"
  value       = azurerm_sql_elasticpool.this.pool_size
}

output "this" {
  value = azurerm_sql_elasticpool.this
}
```

[top](#index)