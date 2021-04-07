# azurerm_synapse_sql_pool

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
module "azurerm_synapse_sql_pool" {
  source = "./modules/azurerm/r/azurerm_synapse_sql_pool"

  # collation - (optional) is a type of string
  collation = null
  # create_mode - (optional) is a type of string
  create_mode = null
  # data_encrypted - (optional) is a type of bool
  data_encrypted = null
  # name - (required) is a type of string
  name = null
  # recovery_database_id - (optional) is a type of string
  recovery_database_id = null
  # sku_name - (required) is a type of string
  sku_name = null
  # synapse_workspace_id - (required) is a type of string
  synapse_workspace_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  restore = [{
    point_in_time      = null
    source_database_id = null
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
variable "collation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "create_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "recovery_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "synapse_workspace_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "restore" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      point_in_time      = string
      source_database_id = string
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
resource "azurerm_synapse_sql_pool" "this" {
  # collation - (optional) is a type of string
  collation = var.collation
  # create_mode - (optional) is a type of string
  create_mode = var.create_mode
  # data_encrypted - (optional) is a type of bool
  data_encrypted = var.data_encrypted
  # name - (required) is a type of string
  name = var.name
  # recovery_database_id - (optional) is a type of string
  recovery_database_id = var.recovery_database_id
  # sku_name - (required) is a type of string
  sku_name = var.sku_name
  # synapse_workspace_id - (required) is a type of string
  synapse_workspace_id = var.synapse_workspace_id
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "restore" {
    for_each = var.restore
    content {
      # point_in_time - (required) is a type of string
      point_in_time = restore.value["point_in_time"]
      # source_database_id - (required) is a type of string
      source_database_id = restore.value["source_database_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "collation" {
  description = "returns a string"
  value       = azurerm_synapse_sql_pool.this.collation
}

output "id" {
  description = "returns a string"
  value       = azurerm_synapse_sql_pool.this.id
}

output "this" {
  value = azurerm_synapse_sql_pool.this
}
```

[top](#index)