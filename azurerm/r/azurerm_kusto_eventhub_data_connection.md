# azurerm_kusto_eventhub_data_connection

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
module "azurerm_kusto_eventhub_data_connection" {
  source = "./modules/azurerm/r/azurerm_kusto_eventhub_data_connection"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # compression - (optional) is a type of string
  compression = null
  # consumer_group - (required) is a type of string
  consumer_group = null
  # data_format - (optional) is a type of string
  data_format = null
  # database_name - (required) is a type of string
  database_name = null
  # event_system_properties - (optional) is a type of list of string
  event_system_properties = []
  # eventhub_id - (required) is a type of string
  eventhub_id = null
  # location - (required) is a type of string
  location = null
  # mapping_rule_name - (optional) is a type of string
  mapping_rule_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # table_name - (optional) is a type of string
  table_name = null

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

variable "compression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "consumer_group" {
  description = "(required)"
  type        = string
}

variable "data_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "event_system_properties" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "eventhub_id" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "mapping_rule_name" {
  description = "(optional)"
  type        = string
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

variable "table_name" {
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
resource "azurerm_kusto_eventhub_data_connection" "this" {
  cluster_name            = var.cluster_name
  compression             = var.compression
  consumer_group          = var.consumer_group
  data_format             = var.data_format
  database_name           = var.database_name
  event_system_properties = var.event_system_properties
  eventhub_id             = var.eventhub_id
  location                = var.location
  mapping_rule_name       = var.mapping_rule_name
  name                    = var.name
  resource_group_name     = var.resource_group_name
  table_name              = var.table_name

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
output "event_system_properties" {
  description = "returns a list of string"
  value       = azurerm_kusto_eventhub_data_connection.this.event_system_properties
}

output "id" {
  description = "returns a string"
  value       = azurerm_kusto_eventhub_data_connection.this.id
}

output "this" {
  value = azurerm_kusto_eventhub_data_connection.this
}
```

[top](#index)