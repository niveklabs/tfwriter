# azurerm_kusto_eventgrid_data_connection

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
module "azurerm_kusto_eventgrid_data_connection" {
  source = "./modules/azurerm/r/azurerm_kusto_eventgrid_data_connection"

  # blob_storage_event_type - (optional) is a type of string
  blob_storage_event_type = null
  # cluster_name - (required) is a type of string
  cluster_name = null
  # database_name - (required) is a type of string
  database_name = null
  # eventhub_consumer_group_name - (required) is a type of string
  eventhub_consumer_group_name = null
  # eventhub_id - (required) is a type of string
  eventhub_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # skip_first_record - (optional) is a type of bool
  skip_first_record = null
  # storage_account_id - (required) is a type of string
  storage_account_id = null

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
variable "blob_storage_event_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "eventhub_consumer_group_name" {
  description = "(required)"
  type        = string
}

variable "eventhub_id" {
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "skip_first_record" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_account_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_kusto_eventgrid_data_connection" "this" {
  blob_storage_event_type      = var.blob_storage_event_type
  cluster_name                 = var.cluster_name
  database_name                = var.database_name
  eventhub_consumer_group_name = var.eventhub_consumer_group_name
  eventhub_id                  = var.eventhub_id
  location                     = var.location
  name                         = var.name
  resource_group_name          = var.resource_group_name
  skip_first_record            = var.skip_first_record
  storage_account_id           = var.storage_account_id

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
  value       = azurerm_kusto_eventgrid_data_connection.this.id
}

output "this" {
  value = azurerm_kusto_eventgrid_data_connection.this
}
```

[top](#index)