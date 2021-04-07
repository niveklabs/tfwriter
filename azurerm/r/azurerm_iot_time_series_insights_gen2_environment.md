# azurerm_iot_time_series_insights_gen2_environment

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
module "azurerm_iot_time_series_insights_gen2_environment" {
  source = "./modules/azurerm/r/azurerm_iot_time_series_insights_gen2_environment"

  # id_properties - (required) is a type of set of string
  id_properties = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # warm_store_data_retention_time - (optional) is a type of string
  warm_store_data_retention_time = null

  storage = [{
    key  = null
    name = null
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
variable "id_properties" {
  description = "(required)"
  type        = set(string)
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

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "warm_store_data_retention_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      key  = string
      name = string
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
resource "azurerm_iot_time_series_insights_gen2_environment" "this" {
  # id_properties - (required) is a type of set of string
  id_properties = var.id_properties
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku_name - (required) is a type of string
  sku_name = var.sku_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # warm_store_data_retention_time - (optional) is a type of string
  warm_store_data_retention_time = var.warm_store_data_retention_time

  dynamic "storage" {
    for_each = var.storage
    content {
      # key - (required) is a type of string
      key = storage.value["key"]
      # name - (required) is a type of string
      name = storage.value["name"]
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
output "data_access_fqdn" {
  description = "returns a string"
  value       = azurerm_iot_time_series_insights_gen2_environment.this.data_access_fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_iot_time_series_insights_gen2_environment.this.id
}

output "this" {
  value = azurerm_iot_time_series_insights_gen2_environment.this
}
```

[top](#index)