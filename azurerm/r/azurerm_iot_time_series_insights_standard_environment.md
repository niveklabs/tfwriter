# azurerm_iot_time_series_insights_standard_environment

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
module "azurerm_iot_time_series_insights_standard_environment" {
  source = "./modules/azurerm/r/azurerm_iot_time_series_insights_standard_environment"

  # data_retention_time - (required) is a type of string
  data_retention_time = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # partition_key - (optional) is a type of string
  partition_key = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # storage_limit_exceeded_behavior - (optional) is a type of string
  storage_limit_exceeded_behavior = null
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
variable "data_retention_time" {
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

variable "partition_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "storage_limit_exceeded_behavior" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_iot_time_series_insights_standard_environment" "this" {
  # data_retention_time - (required) is a type of string
  data_retention_time = var.data_retention_time
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # partition_key - (optional) is a type of string
  partition_key = var.partition_key
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku_name - (required) is a type of string
  sku_name = var.sku_name
  # storage_limit_exceeded_behavior - (optional) is a type of string
  storage_limit_exceeded_behavior = var.storage_limit_exceeded_behavior
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "id" {
  description = "returns a string"
  value       = azurerm_iot_time_series_insights_standard_environment.this.id
}

output "this" {
  value = azurerm_iot_time_series_insights_standard_environment.this
}
```

[top](#index)